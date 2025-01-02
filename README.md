# Solucion-problema-intel-VT-x-EPT-VMware---VirtualBox
Hola esta es una solucion que encontre al problema de virtualizacion de intel, esto me funciono en windows 11 pro con un procesador de intel i5 - 12th gen

![image](https://github.com/user-attachments/assets/ba3b7b48-b1bb-4af9-bb0c-085330b6de2e)

![image](https://github.com/user-attachments/assets/107fb2e5-e2de-4dd1-be58-1e9911851e58)

Para poder solucionar este problema, supondre que ya revisaron que tengan activado la virtualizacion de intel en la Bios, y aun asi persite el problema por la cual para poder solucionarlo tenemos que realizar lo siguiente:

1-  Desactivar el core insolation de windows.

![image](https://github.com/user-attachments/assets/fe8ac965-7ac9-4b51-bb6b-b8ad8bdc189c)

2- Con el atajo windows + r  pondremos gpedit.msc y buscaremos la siguente opcion y la desactivaremos.

![image](https://github.com/user-attachments/assets/b5a8acc5-23af-4f2c-825d-140d1889d33d)

3- Despues nos iremos a Agregar o quitar caracteristicas de windows: 

![image](https://github.com/user-attachments/assets/43a0f566-0c9b-46b8-894c-0030be1ea434)

Dentro desactivaremos estas opciones: 

![image](https://github.com/user-attachments/assets/0b0478b0-75ce-4a9f-8684-73b26e597bba)

4- Reiniciamos la computadora y al iniciar entremamos en la cmd y ejecutamos este comando systeminfo y verificamos que nos aparezca esto 


