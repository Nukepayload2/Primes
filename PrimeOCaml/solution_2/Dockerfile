FROM primeimages/ocaml:4.12-r1 AS build

WORKDIR /home/opam/primeocaml

COPY *.ml ./

RUN sudo chown -R opam:nogroup .
RUN corebuild PrimeOCamlFunctional.native

FROM alpine:3.13

WORKDIR /app
COPY --from=build /home/opam/primeocaml/PrimeOCamlFunctional.native PrimeOCamlFunctional.native

ENTRYPOINT [ "./PrimeOCamlFunctional.native" ]