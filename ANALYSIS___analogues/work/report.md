---
lang: ru-RU
mainfont: Arial
fontsize: 11pt
geometry: margin=2cm
header-includes: |
  \usepackage{adjustbox}
  \usepackage{array}
  \usepackage{booktabs}
  \usepackage{tabularx}
  \usepackage[table]{xcolor}
  \newcolumntype{Y}{>{\centering\arraybackslash}X}
  \definecolor{plusgreen}{RGB}{0,120,0}
  \definecolor{minusred}{RGB}{180,0,0}
  \definecolor{pmyellow}{RGB}{200,120,0}
  \newcommand{\Plus}{\textcolor{plusgreen}{\textbf{+}}}
  \newcommand{\Minus}{\textcolor{minusred}{\textbf{–}}}
  \newcommand{\PM}{\textcolor{pmyellow}{\textbf{±}}}
  \let\oldtextbf\textbf
  \renewcommand{\textbf}[1]{\oldtextbf{\boldmath #1}}
---

# Сравнительный анализ проекта HSE Random Coffee by hippopotamus

## 1. Сравнение аналогов: плюсы и минусы (визуальная таблица)

\begin{center}
\small
\adjustbox{max width=\textwidth}{
\begin{tabularx}{1.05\textwidth}{>{\bfseries}l *{5}{Y}}
\toprule
\rowcolor{gray!15}
Критерий & HSE Random Coffee & Donut & Meetup & Lunchclub & Внутривузов-\hspace{0pt}ские ивенты \\
\midrule
Университетская аудитория & \Plus & \Minus & \Minus & \Minus & \Plus \\
Офлайн-фокус & \Plus & \PM & \Plus & \PM & \Plus \\
& & \tiny (офлайн только в офисе) & & \tiny (офлайн после онлайн) & \\
Персонализированный мэтчинг & \Plus & \Minus & \Minus & \Plus & \Minus \\
& & \tiny (случайный/по отделу) & \tiny (самостоятельный выбор) & \tiny (ML + цели) & \\
Интеграция с экосистемой & \Plus & \Plus & \Minus & \Minus & \Minus \\
& & \tiny (Slack/Teams) & & & \\
Неформальная атмосфера & \Plus & \Minus & \PM & \Minus & \Minus \\
& & \tiny (корпоративная) & \tiny (зависит от события) & \tiny (профессиональная) & \\
Масштабируемость & \Plus & \Plus & \Plus & \PM & \Minus \\
Коммерческая модель & \Plus & \Plus & \Plus & \Plus & \Minus \\
\bottomrule
\end{tabularx}
}
\end{center}

\bigskip
\noindent\begin{adjustbox}{valign=t,minipage=0.95\textwidth,left=0pt}
\colorbox{gray!5}{%
\begin{minipage}{\dimexpr\textwidth-2\fboxsep\relax}
\leftskip=8pt
\small
\noindent\textbf{Легенда}:\\
\Plus\, — сильное соответствие / преимущество\\
\Minus\, — отсутствие / недостаток\\
\PM\, — частичное соответствие / компромисс
\end{minipage}%
}
\end{adjustbox}
\bigskip

## 2. Детализация по критериям и аудитории

### Аудитория

\begin{center}
\small
\adjustbox{max width=\textwidth}{
\begin{tabularx}{1.05\textwidth}{l *{5}{Y}}
\toprule
\rowcolor{gray!15}
Аудитория & HSE Random Coffee & Donut & Meetup & Lunchclub & Внутривузов-\hspace{0pt}ские ивенты \\
\midrule
Студенты ВШЭ & \Plus & \Minus & \Minus & \Minus & \Plus \\
Преподаватели ВШЭ & \Plus & \Minus & \Minus & \Minus & \Plus \\
Выпускники ВШЭ & \Plus & \Minus & \Minus & \Minus & \Minus \\
Сотрудники компаний & \Minus & \Plus & \Minus & \Plus & \Minus \\
Глобальная публика & \Minus & \Minus & \Plus & \Plus & \Minus \\
\bottomrule
\end{tabularx}
}
\end{center}

\bigskip

### Формат взаимодействия

\begin{center}
\small
\adjustbox{max width=\textwidth}{
\begin{tabularx}{1.05\textwidth}{l *{5}{Y}}
\toprule
\rowcolor{gray!15}
Формат & HSE Random Coffee & Donut & Meetup & Lunchclub & Внутривузов-\hspace{0pt}ские ивенты \\
\midrule
Офлайн 1:1 & \Plus & \PM & \Minus & \PM & \Plus \\
Онлайн 1:1 & \Minus & \Plus & \Minus & \Plus & \Minus \\
Групповые встречи & \Minus & \PM & \Plus & \Minus & \Plus \\
Кофейня/коворкинг как локация & \Plus & \Minus & \PM & \PM & \PM \\
\bottomrule
\end{tabularx}
}
\end{center}

\bigskip

### Механизм мэтчинга

\begin{center}
\small
\begin{adjustbox}{max width=\textwidth}
\begin{tabularx}{1.05\textwidth}{>{\raggedright\arraybackslash}p{4.5cm} *{5}{>{\centering\arraybackslash}X}}
\toprule
\rowcolor{gray!15}
Механизм & HSE Random Coffee & Donut & Meetup & Lunchclub & Внутривузов\hspace{0pt}ские ивенты \\
\midrule
Rule-based по целям/интересам 
& \Plus 
& \Minus 
& \Minus 
& \Minus 
& \Minus \\[2pt]

ML-мэтчинг 
& \Minus\par{\scriptsize(план)} 
& \Minus 
& \Minus 
& \Plus 
& \Minus \\[2pt]

Случайный 
& \Minus 
& \Plus 
& \Minus 
& \Minus 
& \Minus \\[2pt]

Самостоятельный выбор 
& \Minus 
& \Minus 
& \Plus 
& \Minus 
& \Minus \\[2pt]

Ручной подбор 
& \Minus 
& \Minus 
& \Minus 
& \PM\par{\scriptsize(модерация)} 
& \Plus \\[2pt]
\bottomrule
\end{tabularx}
\end{adjustbox}
\end{center}

\bigskip

### Интеграции

\begin{center}
\small
\adjustbox{max width=\textwidth}{
\begin{tabularx}{1.05\textwidth}{l *{5}{Y}}
\toprule
\rowcolor{gray!15}
Интеграция & HSE Random Coffee & Donut & Meetup & Lunchclub & Внутривузовские ивенты \\
\midrule
HSE SSO & \Plus & \Minus & \Minus & \Minus & \Minus \\
Telegram & \Plus & \Minus & \Minus & \Minus & \Minus \\
Google Calendar & \Plus & \Minus & \Minus & \Minus & \Minus \\
Slack / Teams & \Minus & \Plus & \Minus & \Minus & \Minus \\
Email / SMS & \Minus & \PM & \Plus & \Plus & \Plus \\
\bottomrule
\end{tabularx}
}
\end{center}

\bigskip

### Атмосфера и UX

\begin{center}
\small
\adjustbox{max width=\textwidth}{
\begin{tabularx}{1.05\textwidth}{l *{5}{Y}}
\toprule
\rowcolor{gray!15}
Качество & HSE Random Coffee & Donut & Meetup & Lunchclub & Внутривузов-\hspace{0pt}ские ивенты \\
\midrule
Неформальность & \Plus & \Minus & \PM & \Minus & \Minus \\
Низкий порог входа & \Plus & \Plus & \Plus & \Minus & \Plus \\
Дружелюбный интерфейс & \Plus & \PM & \PM & \PM & \Minus \\
Отсутствие давления & \Plus & \PM & \PM & \Minus & \PM \\
\bottomrule
\end{tabularx}
}
\end{center}

\bigskip

### Масштабируемость и монетизация

\begin{center}
\small
\adjustbox{max width=\textwidth}{
\begin{tabularx}{1.05\textwidth}{l *{5}{Y}}
\toprule
\rowcolor{gray!15}
Показатель & HSE Random Coffee & Donut & Meetup & Lunchclub & Внутривузов-\hspace{0pt}ские ивенты \\
\midrule
B2B-масштаб (другие вузы) & \Plus & \Minus & \Minus & \Minus & \Minus \\
B2B-масштаб (компании) & \Plus & \Plus & \Minus & \Plus & \Minus \\
Премиум-функции & \Plus & \Minus & \Plus & \Plus & \Minus \\
Партнёрства (кофейни и др.) & \Plus & \Minus & \Minus & \Minus & \Minus \\
Органический рост & \Plus & \Plus & \Plus & \PM & \Minus \\
\bottomrule
\end{tabularx}
}
\end{center}

\bigskip

## 3. Ключевые выводы (визуально подтверждённые)

- **HSE Random Coffee — единственный продукт**, который получает **«\Plus» по всем ключевым критериям**, релевантным **университетской среде**.
- **Lunchclub** силён в мэтчинге, но **проваливается по аудитории и атмосфере** для студентов.
- **Donut** отлично работает в корпорациях, но **не решает задачи межфакультетного общения**.
- **Внутривузовские ивенты** — единственный аналог с «\Plus» по аудитории и офлайн-формату, но **полностью проигрывают по автоматизации, масштабу и UX**.

> **Итог**: HSE Random Coffee заполняет **уникальную нишу** — **цифровой, неформальный, офлайн-ориентированный нетворкинг внутри вуза**. Ни один аналог не покрывает этот сценарий комплексно.