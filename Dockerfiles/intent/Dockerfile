# from rasa base image
FROM rasa/rasa:3.6.16
# copy all source and the Rasa generated model
COPY ./intent/ /app

# inform which port will run on
EXPOSE 5005

USER root

ENTRYPOINT []
ENV shell_mode false

RUN rasa train nlu

# launch script (rasa shell or rasa run)
CMD sh -c 'if [ "$shell_mode" = false ]; then rasa run --enable-api -p 5005 --cors "*"; else rasa shell --enable-api -p 5005; fi'