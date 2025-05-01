```latexsvg
\documentclass{article}
\usepackage{tikz}
\begin{document}

\begin{tikzpicture}[scale = 1.5]
    % Draw the x-axis
    \draw[->] (-2,0) -- (3,0) node[right] {$x$};
    % Draw the y-axis
    \draw[->] (0,-2) -- (0,3) node[above] {$y$};

    % Plot the floor function
    \draw[thick, blue] (-2,-2) -- (-1,-2) -- (-1,-1) -- (0,-1) -- (0,0) -- (1,0) -- (1,1) -- (2,1) -- (2,2) -- (3,2);
    \node[below left] at (-2,-2) {$\lfloor x \rfloor$};

    % Plot the ceiling function
    \draw[thick, red] (-2,-1) -- (-1,-1) -- (-1,0) -- (0,0) -- (0,1) -- (1,1) -- (1,2) -- (2,2) -- (2,3) -- (3,3);
    \node[below left] at (-2,-1) {$\lceil x \rceil$};

    % Add some grid lines for better visualization
    \draw[help lines, dashed] (-2,-2) grid (3,3);
\end{tikzpicture}

\end{document}
```

```latexsvg
\documentclass{article}
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[scale=2]
    % 绘制坐标轴
    \draw[->] (-2.2,0) -- (2.2,0) node[right] {$x$};
    \draw[->] (0,-0.2) -- (0,1.2) node[above] {$y$};
    % 绘制函数图像
    \foreach \x in {-2,-1,0,1} {
        \draw[blue,thick] (\x,0) -- (\x+1,1);
        \filldraw[white] (\x+1,1) circle (0.03);
        \filldraw[blue] (\x+1,0) circle (0.03);
    }
    % 添加刻度和标签
    \foreach \x in {-2,-1,1,2} {
        \draw (\x,0.05) -- (\x,-0.05) node[below] {$\x$};
    }
    \foreach \y in {1} {
        \draw (0.05,\y) -- (-0.05,\y) node[left] {$\y$};
    }
\end{tikzpicture}
\end{document}    
```

$\lfloor x+n \rfloor = \lfloor x \rfloor + n$
$$
	x=\lfloor x\rfloor + \{x\}
$$
向下取整删除小数部分即可
$$
	\lfloor x\rfloor=\lfloor\lfloor x\rfloor + \{x\}\rfloor
$$
向下取整删除小数部分，并去掉外层取整符号
$$
	\lfloor x+n \rfloor = \lfloor \lfloor x\rfloor + \{x\}+n \rfloor= \lfloor x\rfloor +n
$$
![[取整不等式]]