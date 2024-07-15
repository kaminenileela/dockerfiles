ARG version
FROM almalinux:${version:-8}
ARG COURSE
ARG TRAINER
ARG Duration=120HRS
ENV Duration=${Duration}
RUN echo "Course is: ${COURSE}, Trainer is: ${TRAINER}, Duraion is: ${Duration}"
CMD ["sleep","100"]