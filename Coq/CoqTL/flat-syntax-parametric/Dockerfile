FROM ocaml/opam2


RUN sudo apt update\
&& sudo apt install curl -y\
&& sudo apt install m4 -y\
&& opam pin add coq 8.11.1\
&& eval $(opam env)\
&& cd ..\
&& git clone -b flat-syntax-parametric https://github.com/atlanmod/CoqTL.git\
&& cd CoqTL\
&& cd fr.inria.atlanmod.coqtl.coq\
&& git clean -fdx\
&& coq_makefile -f _CoqProject -o Makefile\
&& make
