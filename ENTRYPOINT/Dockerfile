FROM almalinux:9
#CMD ["ping","-c5", "google.com" ] 
# when given docker run entrypoint:1.0.0 ping -c5 yahoo.com this CMD command overrides.
# same instruction trying to override with ENTRYPOINT is not working.you cant override ENTRYPOINT, if you try to do it will go append.
#ENTRYPOINT [ "ping", "-c5", "google.com"]
CMD ["google.com" ] 
#CMD is argument
ENTRYPOINT [ "ping", "-c5"] 
#ENTRYPOINT is instruction
#you can mix cmd and entrypoint for better results 
