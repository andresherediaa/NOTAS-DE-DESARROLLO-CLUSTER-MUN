# NOTAS-DE-DESARROLLO-CLUSTER-MUN

ERROR:
    SE REPORTA QUE NO HAY SERVICIO EN LOS TICKETS DE TRANVIA, NO SE PUEDE HACER TELNET Y NINGUN SERVCIO ESTA ACCESIBLE DESDE FUERA O DENTRO DEL CLUSTER

SOLUCION:
    1. REVISAR QUE EL DEPLOY DEL SERVICIO DE TICKETS ESTE LEVANTADO CON ESTADO 1/1
    2. REVISAR QUE EL DEPLOY DEL AMBASSADOR ESTE LEVANTADO Y NO SE HAYA REINICIADO RECIENTEMENTE

    STEPS:
        A. kubectl get pods -n ambassador //revisa que no se haya reiniciado el pod de ambasador recientemente
        B. kubectl logs ambassador-69c494ddb8-h5c4v -n ambassador //checa logs
        C. kubectl get deploy -n ambassador
        D. kubectl rollout restart deploy ambassador -n ambassador //REINICA EMBASSADDOR

    CON ELLO DEBERIA FUNCIONAR
       





