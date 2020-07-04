FROM ocaml/opam2


RUN sudo apt update\
&& sudo apt install curl -y\
&& sudo apt install m4 -y\
&& opam pin add coq 8.11.1\
&& eval $(opam env)\
&& cd ..\
&& git clone https://github.com/atlanmod/CoqTL.git\
&& cd CoqTL\
&& cd fr.inria.atlanmod.coqtl.coq\
&& git clean -fdx\
&& rm _CoqProject

ADD _CoqProject .

RUN  coq_makefile -f _CoqProject -o Makefile\
&& make
