---
lang: ru-RU
mainfont: Arial
fontsize: 11pt
geometry: margin=2cm
anchor: false
header-includes: |
  \usepackage[unicode, pdfencoding=auto]{hyperref}
  \usepackage{adjustbox}
  \usepackage{array}
  \usepackage{booktabs}
  \usepackage{tikz}
  \usepackage{multirow}
  \usetikzlibrary{positioning}
  \usepackage{tabularx}
  \usepackage[table]{xcolor}
  \newcolumntype{Y}{>{\centering\arraybackslash}X}
  \definecolor{plusgreen}{RGB}{0,120,0}
  \definecolor{minusred}{RGB}{180,0,0}
  \definecolor{pmyellow}{RGB}{200,120,0}
  \newcommand{\Plus}{\textcolor{plusgreen}{\textbf{+}}}
  \newcommand{\Minus}{\textcolor{minusred}{\textbf{–}}}
  \newcommand{\PM}{\textcolor{pmyellow}{\textbf{±}}}
---
# Анализ бизнес-процессов HSE Random Coffee

## Общая схема жизненного цикла пользователя

\begin{center}
\begin{tikzpicture}[
  >=stealth,
  thick,
  font=\small,
  every node/.style={align=center, text width=2.8cm, inner sep=6pt}
]

\node (reg) at (90:3cm) {Регистрация};
\node (prof) at (30:3cm) {Профилирование};
\node (match) at (-30:3cm) {Мэтчинг};
\node (org) at (-90:3cm) {Организация встречи};
\node (meet) at (-150:3cm) {Проведение встречи};
\node (fb) at (150:3cm) {Обратная связь};

\draw[->, thick] (reg) to[bend left=15] (prof);
\draw[->, thick] (prof) to[bend left=15] (match);
\draw[->, thick] (match) to[bend left=15] (org);
\draw[->, thick] (org) to[bend left=15] (meet);
\draw[->, thick] (meet) to[bend left=15] (fb);
\draw[->, thick] (fb) to[bend left=15] (prof);

\end{tikzpicture}
\end{center}

\vspace{1em}
Каждый этап — автоматизированный, без ручного вмешательства, с интеграцией в привычные пользователю инструменты (Telegram, Google Calendar).

\bigskip

\begin{center}
\begin{minipage}{\textwidth}
\noindent\textbf{Сравнение бизнес-процессов с аналогами}

\small
\begin{adjustbox}{max width=\textwidth}
\begin{tabularx}{\textwidth}{>{\raggedright\arraybackslash}p{4.3cm} *{5}{>{\centering\arraybackslash}X}}
\toprule
\rowcolor{gray!15}
Бизнес-процесс & HSE Random Coffee & Donut & Meetup & Lunchclub & Внутривузов\hspace{0pt}ские ивенты \\
\midrule
Автоматическая регистрация 
& \Plus\par{\scriptsize(HSE SSO)} 
& \Plus\par{\scriptsize(Slack)} 
& \Minus\par{\scriptsize(ручная)} 
& \Minus\par{\scriptsize(ручная + модерация)} 
& \Minus\par{\scriptsize(рассылка/афиши)} \\[2pt]

Персонализированный профиль 
& \Plus\par{\scriptsize(цели, интересы, факультет)} 
& \Minus\par{\scriptsize(только отдел/роль)} 
& \PM\par{\scriptsize(интересы, но без целей)} 
& \Plus\par{\scriptsize(резюме, цели)} 
& \Minus \\[2pt]

Автоматический мэтчинг 
& \Plus\par{\scriptsize(rule-based, раз в неделю)} 
& \Plus\par{\scriptsize(случайный)} 
& \Minus\par{\scriptsize(самостоятельный выбор)} 
& \Plus\par{\scriptsize(ML + модерация)} 
& \Minus \\[2pt]

Интеграция с календарём 
& \Plus\par{\scriptsize(Google Calendar)} 
& \PM\par{\scriptsize(через Slack)} 
& \Minus & \Minus & \Minus \\[2pt]

Уведомления в мессенджере 
& \Plus\par{\scriptsize(Telegram Bot)} 
& \Plus\par{\scriptsize(Slack)} 
& \Minus & \Minus & \Minus \\[2pt]

Офлайн-встреча по умолчанию 
& \Plus 
& \PM\par{\scriptsize(офлайн только в офисе)} 
& \Plus 
& \PM\par{\scriptsize(офлайн — опционально)} 
& \Plus \\[2pt]

Обратная связь после встречи 
& \Plus\par{\scriptsize(Telegram-опрос)} 
& \PM\par{\scriptsize(опционально)} 
& \Minus 
& \Plus\par{\scriptsize(в приложении)} 
& \Minus \\[2pt]

Цикличность (еженедельно) 
& \Plus & \Plus & \Minus & \Plus & \Minus \\[2pt]

Data-driven улучшение 
& \Plus\par{\scriptsize(план: ML на основе отзывов)} 
& \Minus & \Minus & \Plus & \Minus \\[2pt]

Минимальный порог входа 
& \Plus\par{\scriptsize(всё в Telegram)} 
& \Plus & \PM & \Minus\par{\scriptsize(резюме, ожидания)} 
& \Plus \\[2pt]

\bottomrule
\end{tabularx}
\end{adjustbox}

\vspace{4pt}
\colorbox{gray!5}{%
\begin{minipage}{\textwidth}
\leftskip=8pt
\small
\textbf{Легенда:}\\
\Plus\, — процесс полностью автоматизирован и оптимизирован\\
\Minus\, — отсутствует или полностью ручной\\
\PM\, — частично реализован или требует усилий от пользователя
\end{minipage}%
}
\end{minipage}
\end{center}



## Ключевые особенности бизнес-процессов HSE Random Coffee

\begin{center}
\small
\adjustbox{max width=\textwidth}{
\begin{tabularx}{1.1\textwidth}{>{\raggedright\arraybackslash}p{4.5cm} >{\raggedright\arraybackslash}X >{\raggedright\arraybackslash}X}
\toprule
\rowcolor{gray!15}
Особенность & Описание & Преимущество \\
\midrule
Цикличность & Процесс повторяется каждую неделю → формирует привычку & Повышает retention и вовлечённость \\
Экосистемность & Все этапы — внутри Telegram + Google Calendar & Нет необходимости в отдельном приложении \\
Автоматизация & От регистрации до отзыва — без админов & Масштабируемость, низкие операционные издержки \\
Фокус на офлайн & Встреча — не опция, а ядро процесса & Глубина контакта, социальный эффект \\
Замкнутый цикл данных & Отзыв → улучшение мэтчинга → лучшие пары → больше отзывов & Самообучающаяся система (в будущем — ML) \\
Низкий порог входа & Нет резюме, нет модерации, нет сложных форм & Максимальная инклюзивность для новичков \\
\bottomrule
\end{tabularx}
}
\end{center}

\bigskip

## Уникальные бизнес-процессы (отсутствующие у аналогов)

\begin{center}
\small
\adjustbox{max width=\textwidth}{
\begin{tabularx}{1.0\textwidth}{>{\raggedright\arraybackslash}p{6cm} >{\centering\arraybackslash}X >{\centering\arraybackslash}X}
\toprule
\rowcolor{gray!15}
Процесс & HSE Random Coffee & Аналоги \\
\midrule
Межфакультетный мэтчинг по умолчанию & \Plus & \Minus \\
Интеграция с университетской SSO & \Plus & \Minus \\
Партнёрские локации (кофейни) как часть UX & \Plus & \Minus \\
Тематические недели («Random Coffee Week») & \Plus & \Minus \\
Вовлечение студенческих лидеров как амбассадоров & \Plus & \Minus \\
\bottomrule
\end{tabularx}
}
\end{center}

> Эти процессы делают платформу **не просто техническим решением**, а **социальным инструментом**, встроенным в культуру ВШЭ.

\bigskip

## Вывод по бизнес-процессам

- **HSE Random Coffee — единственный проект**, где **все бизнес-процессы** выстроены вокруг **офлайн-встречи в университетской среде**.
- Аналоги либо **игнорируют офлайн**, либо **работают вне академического контекста**.
- **Автоматизация + интеграция + цикличность** создают **самоподдерживающуюся систему** с минимальными затратами на поддержку.
- **Данные → улучшение → лояльность** — заложена основа для перехода к **интеллектуальному мэтчингу**.

> **Итог**: бизнес-процессы не просто «работают» — они **усиливают миссию проекта**: создавать живое, сплочённое сообщество Вышки через простые, регулярные, осмысленные встречи.
