# On the Geometry of a Fake Projective Plane with 21 Automorphisms
This repository contains supplementary code for the paper "On the Geometry of a Fake Projective Plane with $21$ Automorphisms".

## Main Files

The main files are laid out in the current directory as follows. Unless specified otherwise, files with suffix **.txt** are Magma files.

### Mathematica Files
- [3H-Torsion.nb](3H-Torsion.nb) : 
    1. Produces linear cuts representing $3H + T$ for all non-trivial torsion divisors $T$ from the outputs of [3H-Reduction.txt](3H-Reduction.txt). 
    2. Determines the group relations between the torsion divisors.
    3. Computes explicit quadratics vanishing on the sections $3H + D$, $3H + D_1$, and $3H + D + D_1$.
- [4H.nb](4H.nb) : 
    1. Produces relations on $s_3 = r_3^3$ and $d = r_3 r_5 r_6$ and finds a solution to $s_3$ and $d$.
    2. The intermediate calculation for solving the relations is done in the Magma file [4H-Quadratic.txt](4H-Quadratic.txt).
    3. Calculates the explicit quadratics vanishing on $4H$ based on this. 
- [5H-Torsion.nb](5H-Torsion.nb) :
    1. Produces an embedding of the fake projective plane into $\mathbb{C}P^6$ using sections of $5H + D$.
    2. Produces a map of the fake projective plane into $\mathbb{C}P^6$ using sections of $5H$. This image of the fake projective plane will turn out to be singular.
    3. Computes explicit quadratics vanishing on the basis of $6$ global sections of $5H$.
- [4H-Torsion.nb](4H-Torsion.nb) : Computes explicit quadratics vanishing on the sections $4H + D$, $4H + D_1$, and $4H + D + D_1$ and checks that $2H + D_1$ and $2H + D + D_1$ has no non-trivial sections.

### Magma Files
- [3H-Reduction.txt](3H-Reduction.txt) finds two finite field solutions of linear cuts representing $3H + D_1$ and $3H + D + D_1$.
- [4H-Quadratic.txt](4H-Quadratic.txt) solves the relations on coefficients of $s_3 = r_3^3$ and $d = r_3 r_5 r_6$ produced by the file [4H.nb](4H.nb).
- [5H-is-prime.txt](5H-is-prime.txt) checks that the $59$ equations produced for $5H$ forms a prime ideal, hence they are no higher degree equations contributing to the image of the FPP.
- [5H-intersection.txt](5H-intersection.txt) checks that the $6$ sections of $5H$ produced in [5H-Torsion.nb](5H-Torsion.nb) does not have any common zeroes.
- [4H-Torsion-intersection.txt](4H-Torsion-intersection.txt) checks that $4H + D, 4H + D_1, 4H + D + D_1$ are basepoint free. It also double checks that $4H$ is not basepoint free.

While all files can be executed independently on their own, the recommended order to run them are:
1. [3H-Reduction.txt](3H-Reduction.txt)
2. [3H-Torsion.nb](3H-Torsion.nb)
3. [4H.nb](4H.nb)
4. [4H-Quadratic.txt](4H-Quadratic.txt)
5. [5H-Torsion.nb](5H-Torsion.nb)
6. [5H-is-prime.txt](5H-is-prime.txt)
7. [5H-intersection.txt](5H-intersection.txt)
8. [4H-Torsion.nb](4H-Torsion.nb)
9. [4H-Torsion-intersection.txt](4H-Torsion-intersection.txt)

This was the order of how we computed the results in this paper. 

## Other Folders
The folders for this repository are as follows:
- [Dependency](Dependency) : Contains pre-computed points and dependencies the main Mathematica files need to run. 
- [Equations](Equations) : Contains data produced by the main Mathematica files.
    - **3H_D.txt** contains the 28 quadratic equations vanishing on $3H + D$.
    - **3H_D+D1.txt** contains the 28 quadratic equations vanishing on $3H + D + D_1$.
    - **3H_D1.txt** contains the 28 quadratic equations vanishing on $3H + D_1$.
    - **4H_Coeffs_Vanishing.txt** contains the relations on the coefficients of $s_3 = r_3^3$ and $d = r_3 r_5 r_6$ produced by [4H.nb](4H.nb).
    - **4H_one_section.txt** contains the 21 quadratics vanishing on $r_3$.
    - **4HD_one_section.txt** contains the 21 quadratics vanishing on one section of $4H + D$.
    - **4HD1_one_section.txt** contains the 21 quadratics vanishing on one section of $4H + D_1$.
    - **4HDD1_one_section.txt** contains the 21 quadratics vanishing on one section of $4H + D + D_1$.
    - **5H_Equations.txt** contains the equations of the map of the fake projective plane into $\mathbb{C}P^6$ using sections of $5H$.
    - **5H_Sections.txt** contains the $6$ global sections of $5H$.
    - **5H+D_Embedding.txt** contains the equations of the embedding of the fake projective plane into $\mathbb{C}P^6$ using sections of $5H + D$.
    - **5H+D_Sections.txt** contains the $6$ global sections of $5H + D$.
    - **Quadratics_on_Zi.txt** contains the quadratics vanishing on each of the $6$ sections of $5H$.
    - **s3_and_D.txt** contains the equations for $s_3 = r_3^3$ and $d = r_3 r_5 r_6$.

- [Verification](Verification) : Contains code verifying the results produced by the main Mathematica files.
    - The folder [5H+D](Verification/5H+D/) checks that the map produced by $5H + D$ is an embedding:
        - **check_hilbert.txt** checks the Hilbert polynomial of the embedding.
        - **check_smoothness** checks that the image is smooth.
        - **check_Macaulay2** performs other checks on the equations.
    - The folder [5H](Verification/5H/):
        - **check_hilbert.txt** shows that the Hilbert polynomial of the equations is $-3$ off from the embedding.
        - **check_Z2.txt** checks the Hilbert polynomial of the quadratics vanishing on $Z_2$ (the main section of $5H$ we used in the paper and calculations). The file is in Macaulay2.
    - The folders [3H+Torsion](Verification/3H+Torsion/) checks the Hilbert polynomial of sections produced on $3H + D, 3H + D_1,$ and $3H + D + D_1$. The files are in Macaulay2.
    - The folders [4H+Torsion](Verification/4H+Torsion/) checks the Hilbert polynomial of one section of $4H, 4H + D, 4H + D_1$, and $4H + D + D_1$ respectively. The files are in Macaulay2.
