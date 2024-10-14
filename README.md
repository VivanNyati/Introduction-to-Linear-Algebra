\documentclass{article}
\usepackage{graphicx}
\usepackage{amsmath,amssymb}
\usepackage{amsfonts}

\title{An Introduction to Determinants, Eigenvalues, and Eigenvectors}
\author{Vivan Nyati}
\date{June 2024}

\begin{document}

\maketitle

\section*{Determinants}

The determinant is defined to be a function represented by 

\[
\text{$\det(A)$ where $A$ is a square matrix}
\]

\vspace{1mm}

that produces a number in the field of the matrix's entries which satisfies the following properties:

\begin{enumerate}
    \item Doing a line\footnote{Line refers to either a row or a column} addition (also known as line replacement) on \(A\) does not change \(\det(A)\).
    \item Scaling a line of \(A\) by a scalar \(k\) multiplies the determinant by \(k\).
    \item Swapping two lines of a matrix multiplies the determinant by \(-1\).
    \item The determinant of the identity matrix \(I_n\) is equal to 1 (where \(n\) represents the \(n \times n\) dimensions).
\end{enumerate}

Therefore, the elementary matrices that apply these types of operations modify the determinant as follows:

\begin{enumerate}
    \item \(\det(EA) = \det(E)\det(A)\) and \(\det(AE) = \det(A)\det(E)\) if \(E\) is the elementary matrix that does line addition because \(\det(E) = 1\) and line addition doesn't change the determinant of A.
    \item \(\det(EA) = \det(E)\det(A)\) and \(\det(AE) = \det(A)\det(E)\) if \(E\) is the elementary matrix that multiplies a line by a constant k because \(\det(E) = k\) and line scaling by k increases the determinant by a factor of k.
    \item \(\det(EA) = \det(E)\det(A)\) and \(\det(AE) = \det(A)\det(E)\) if \(E\) is the elementary matrix that swaps two lines because \(\det(E) = -1\) and line swapping changes the sign of the determinant (multiplies the determinant by -1).
\end{enumerate}

Following this, the elementary matrices' determinants are modified like such when transposed:

\begin{enumerate}
    \item \(\det(E) = \det(E^T)\) if \(E\) is the elementary matrix that line replaces since the transpose of this elementary matrix changes the line addition from row to column or column to row. Since both row and column replacement act the same way with the determinant, \(\det(E) = \det(E^T) = 1\).
    \item \(\det(E) = \det(E^T)\) if \(E\) is the elementary matrix that multiplies a line by a constant \(k\) since the transpose of this elementary matrix doesn't change it, and when \(E = E^T\), \(\det(E) = \det(E^T) = k\).
    \item \(\det(E) = \det(E^T)\) if \(E\) is the elementary matrix that swaps two lines because swapping two lines changes the sign of the determinant, and the transposition of this elementary matrix changes the line swapping from row to column or column to row. Since both row and column swapping act the same way with the determinant, \(\det(E) = \det(E^T) = -1\).
\end{enumerate}

Since these are the three types of elementary matrices, we find that for $\forall$ elementary matrix $E$ and matrix $A \in \mathbb{R}^{\hspace{0.5mm}n \times n}$, \hspace{-0.5mm}$\det(EA) = \det(E)\det(A)$, $\det(AE) = \det(A)\det(E)$, and $\det(E) = \det(E^T)$.

\vspace{3mm}

There are many useful characteristics of determinants that arise due to their nature:
\vspace{3mm}


1. \textbf{Singleton Determinant Rule}
\[
\text{$\det(A) = A_{1,1} \forall A \in \mathbb{R}^{1 \times 1}$}
\]
\[
\text{because if you scale $I_{1 \times 1}$ by $k$, you get a matrix $A$ $\in \mathbb{R}^{1 \times 1}$\hspace{-0.25mm} with}
\]
\[
\text{an entry equal to the scalar. Based on the definition of a determinant, the}
\]
\[
\text{ determinant would be $k \times \det(I_{1 \times 1})$ $\rightarrow$ $k \times 1$ $\rightarrow$ $k$. Since $k$ would also}
\]
\[
\text{be the single entry of $A$ $\in \mathbb{R}^{1 \times 1}$\hspace{-0.25mm}, $\det(A) = A_{1,1} \forall A \in \mathbb{R}^{1 \times 1}$\hspace{-0.3mm}.}
\]

2. \textbf{Determinant Inverse Rule}

\[
\det(A) = 0 \Longleftrightarrow \nexists A^{-1}
\]
\[
\text{because }
\]

3. \textbf{Determinant Product Rule}:
\[
\text{$\det(AB) = \det(A) \times \det(B)$}
\]
\[
\text{because for AB to be invertible, $(AB)^{-1}$ must exist such that $AB (AB)^{-1} = I$.}
\]
\[
\text{Through the associative property of matrices we see that $A \left( B (AB)^{-1} \right) = I$,}
\]
\[
\vspace{1mm}
\text{and therefore ‌ $B (AB)^{-1} = A^{-1}$, which would contradict the fact that $A$ is not}
\]
\[
\text{invertible. Therefore, $AB$ is non-invertible only when if $A$ is non-invertible,}
\]
\[
\text{meaning that $\det(AB)  = \det(A)\det(B)$ = 0 when A is non-invertible. When}
\]
\[
\text{$A$ is invertible, it can be written as the product of elementary matrices}
\]
\[
\text{($A = \prod_{k=1}^{n} E_k$,) and since $\det(\prod_{k=1}^{n} E_k \times B)$ expands to $\det(\prod_{k=1}^{n} E_k) \times \det(B)$}
\]
\[
\text{due to the elementary product property, $\det(AB) = \det(A)\det(B)$ when $A$}
\]
\[
\text{is invertible. Therefore, $\forall A, B \in \mathbb{R}^{\hspace{0.5mm}n \times n}$\hspace{-0.5mm}, $\det(AB) = \det(A) \det(B)$.}
\]

4. \textbf{Determinant Transposition Rule}
\[
\text{$\det(A) = \det(A^T)$}
\]
\[
\text{because if $A$ is invertible, $AA^{-1} = A^{-1}A = I_n$, hence,}
\]
\[
\text{$(AA^{-1})^T = (A^{-1}A)^T = I^T$, expanding to $(A^{-1})^TA^T = A^T(A^{-1})^T = I$,}
\]
\[
\text{due to the transpose of a product property. From this, we see that $A^T$ is}
\]
\[
\text{invertible with its inverse being $(A^{-1})^T\hspace{-0.5mm}$. If and only if $A$ is non-invertible is}
\]
\[
\text{$A^T$ non-invertible. So when $A$ is non-invertible, $\det(A) = \det(A^T) = 0$.}
\]
\[
\text{ When $A$ is invertible, it can be written as the product of elementary}
\]
\[
\text{matrices. Therefore, $A^T$ can be written as $(\prod_{k=1}^{n} E_k)^T$. Through the tranpose}
\] 
\[
\text{of a product property, $A^T$ becomes $\prod_{k=1}^{n} (E_{n-k+1})^T$. Since $\det(E^T) = \det(E)$}
\]
\[
\text{$\forall E$, $A^T = \prod_{k=1}^{n} E_{n-k+1}$. Therefore, $\det(A^T) = \det(\prod_{k=1}^{n} E_{n-k+1})$. Through}
\]
\[
\text{the determinant product rule, we see that $\det(A^T) = \prod_{k=1}^{n} \det(E_{n-k+1})$.}
\]
\[
\text{which rearranging becomes $\det(A^T) = \prod_{k=1}^{n} \det(E_k)$. Rearranging again turns}
\]
\[
\text{into $\det(\prod_{k=1}^{n} E_k)$ = $\det(A^T)$ through the determinant product rule. Since}
\]
\[
\text{$\prod_{k=1}^{n} E_k$ = $A$, $\det(A) = \det(A^T)$. As such, $\forall A \in \mathbb{R}^{\hspace{0.5mm}n \times n}$ \hspace{-1.5mm}, $\det(A) = \det(A^T)$.}
\]
\vspace{1mm}

5. \textbf{Determinant Inverse Rule}
\[
\text{$(\det(A))^{-1} = \det(A^{-1})$}
\vspace{1mm}
\]
\[
\text{since $\det(I_n)$ = $\det(AA^{-1})$ = 1 = $\det(A)\det(A^{-1})$ due to determinant}
\]
\[
\text{rproduct rule, and therefore, $\frac{1}{\det(A)}$ = $\det(A^{-1})$, the latter which simplifies}
\]
\[
\text{to $(\det(A))^{-1}$. Thus, $\forall A \in \mathbb{R}^{\hspace{0.5mm}n \times n}$ \hspace{-1.5mm}, where $A^{-1}$ exists, $(\det(A))^{-1} = \det(A^{-1})$.}
\vspace{1mm}
\]

6. \textbf{Determinant Scalar Product Rule}:
\[
\det(kA) = k^n \det(A)
\]
\[
\text{since $n$ represents how many rows would be multiplied and for every row in}
\vspace{2mm}
\]
\[
\text{$A$ multiplied by $k$, the determinant scales by a factor of $k$, the determinant}
\]
\[
\text{scales by $\prod_{i=1}^n k$ $\rightarrow$ $k^n$. Therefore, $\forall A \in \mathbb{R}^{\hspace{0.5mm}n \times n}$ \hspace{-1.5mm}, $\det(kA) = k^n\det(A)$.}
\]

\vspace{2mm}

7. \textbf{Determinant Power Rule}
\[
\text{$\det(A^n) = \det(A)^n$}
\]
\[
\text{because $\det(A^n)$ expands into $\det(\prod_{i=1}^n A)$, and due to the determinant product}
\vspace{1mm}
\]

\[
\text{rule, becomes $\prod_{i=1}^n \det(A)$. This can be rewritten as $(\det(A))^n$. Thus,}
\vspace{2mm}
\]
\[
\text{$\forall A \in \mathbb{R}^{\hspace{0.5mm}n \times n}$ \hspace{-1.5mm}, $(\det(A))^{-1} = \det(A^{-1})$.}
\vspace{4mm}
\]

Now that we've covered some properties, we can compute determinants. One way to do so is through cofactor expansion:

\[
\text{$\det(A) = \sum_{j=1}^{n} (-1)^{i+j} A_{ij} M_{ij}$ where $A \in \mathbb{R}^{\hspace{0.5mm}n \times n}$}
\]

\begin{enumerate}
    \item \(i\) represents the \(i\)th row of A
    \item \(j\) represents the \(j\)th column of A,
    \item \(A_{ij}\) represents the entry of \(A\) at row \(i\), column \(j\), and
    \item \(M_{ij}\) represents the determinant of the submatrix created by removing the \(i\)th row and \(j\)th column of \(A\).
\end{enumerate}

For example, to find
\[
\begin{vmatrix}
4 & 9 & 2 \\
0 & 0 & 3 \\
1 & 5 & 6
\end{vmatrix}
\]

You can use the entries and minors across the second row, producing:
\[
(-1)^{2+1} \cdot 0 \cdot \begin{vmatrix} 9 & 2 \\ 5 & 6 \end{vmatrix} + (-1)^{2+2} \cdot 0 \cdot \begin{vmatrix} 4 & 2 \\ 1 & 6 \end{vmatrix} + (-1)^{2+3} \cdot 3 \cdot \begin{vmatrix} 4 & 9 \\ 1 & 5 \end{vmatrix}
\]

which simplifies to

\[
(-1)^{2+3} \cdot 3 \cdot \begin{vmatrix} 4 & 9 \\ 1 & 5 \end{vmatrix}.
\]

To find

\[
\begin{vmatrix} 4 & 9 \\ 1 & 5 \end{vmatrix}
\]

You can use the entries and minors across the first row:

\[
\begin{vmatrix} 4 & 9 \\ 1 & 5 \end{vmatrix} = (-1)^{1+1} \cdot 4 \cdot \begin{vmatrix} 5 \end{vmatrix} + (-1)^{1+2} \cdot 9 \cdot \begin{vmatrix} 1 \end{vmatrix}
\]

And due to the $1 \times 1$ determinant rule,

\[
\begin{vmatrix} 4 & 9 \\ 1 & 5 \end{vmatrix} = (-1)^{1+1} \cdot 4 \cdot 5 + (-1)^{1+2} \cdot 9 \cdot 1 \rightarrow 11
\]

Plugging that back into the previous equation, we acquire

\[
(-1)^{2+3} \cdot 3 \cdot 11 \rightarrow -33
\]

Therefore, \[
\begin{vmatrix}
4 & 9 & 2 \\
0 & 0 & 3 \\
1 & 5 & 6
\end{vmatrix}
= -33
\]

\end{document}
