# Solution to Intel VT-x/EPT Problem in VMware and VirtualBox

This guide describes the solution to an issue related to Intel VT-x/EPT virtualization. It was tested on Windows 11 Pro with an Intel i5 12th generation processor.

![Intel VT-x/EPT Issue](https://github.com/user-attachments/assets/ba3b7b48-b1bb-4af9-bb0c-085330b6de2e)

---

## Introduction
To solve this issue, we assume that Intel virtualization is already enabled in the BIOS. If the problem persists, follow the steps below.

---

## Steps to resolve the issue

1. **Verify the message in `systeminfo`**
   - Open a `cmd` window and run `systeminfo`.
   - If the message appears:
     
     ```
     Hypervisor has been detected. Features required for Hyper-V will not be displayed.
     ```
     proceed with the following steps.

2. **Disable Core Isolation**
   - Go to Settings > Device Security > Core Isolation.
   - Turn off this option.

   ![Core Isolation](https://github.com/user-attachments/assets/fe8ac965-7ac9-4b51-bb6b-b8ad8bdc189c)

3. **Modify `gpedit.msc` settings**
   - Press `Windows + R`, type `gpedit.msc`, and navigate to the following option:

     ```
     Computer Configuration > Administrative Templates > System > Virtualization > Turn off Hyper-V
     ```
   - Disable it.

   ![Gpedit Configuration](https://github.com/user-attachments/assets/b5a8acc5-23af-4f2c-825d-140d1889d33d)

4. **Disable Windows features**
   - Go to "Add or Remove Windows Features".
   - Turn off the following options:
     - Virtual Machine Platform
     - Hyper-V
     - Windows Container

   ![Windows Features](https://github.com/user-attachments/assets/43a0f566-0c9b-46b8-894c-0030be1ea434)

5. **Restart and verify**
   - Restart your computer.
   - Open `cmd`, run `systeminfo`, and confirm the following information appears:

     ```
     A hypervisor has not been detected. Features required for Hyper-V will not be displayed.
     ```

   ![Systeminfo Verification](https://github.com/user-attachments/assets/0dfb356f-c5ff-4f96-88ac-0a8f6f92768f)


# Solución al Problema de Intel VT-x/EPT en VMware y VirtualBox

Esta guía describe la solución a un problema relacionado con la virtualización Intel VT-x/EPT. Fue probada en Windows 11 Pro con un procesador Intel i5 de 12ª generación.

![Intel VT-x/EPT Issue](https://github.com/user-attachments/assets/ba3b7b48-b1bb-4af9-bb0c-085330b6de2e)

---

## Introducción
Para resolver este problema, asumimos que la virtualización Intel ya está habilitada en la BIOS. Si el problema persiste, siga los pasos detallados a continuación.

---

## Pasos para solucionar el problema

1. **Verificar el mensaje en `systeminfo`**
   - Abra una ventana de `cmd` y ejecute `systeminfo`.
   - Si aparece el mensaje:
     
     ```
     Hypervisor has been detected. Features required for Hyper-V will not be displayed.
     ```
     continúe con los siguientes pasos.

2. **Desactivar la aislación del núcleo (Core Isolation)**
   - Diríjase a Configuración > Seguridad del dispositivo > Aislación del núcleo.
   - Desactive esta opción.

   ![Core Isolation](https://github.com/user-attachments/assets/fe8ac965-7ac9-4b51-bb6b-b8ad8bdc189c)

3. **Modificar configuración de `gpedit.msc`**
   - Presione `Windows + R`, escriba `gpedit.msc` y busque la siguiente opción:

     ```
     Configuración del equipo > Plantillas administrativas > Sistema > Virtualización > Desactivar Hyper-V
     ```
   - Desactívela.

   ![Gpedit Configuration](https://github.com/user-attachments/assets/b5a8acc5-23af-4f2c-825d-140d1889d33d)

4. **Deshabilitar características de Windows**
   - Vaya a "Agregar o quitar características de Windows".
   - Desactive las siguientes opciones:
     - Plataforma de máquina virtual
     - Hyper-V
     - Contenedor de Windows

   ![Windows Features](https://github.com/user-attachments/assets/43a0f566-0c9b-46b8-894c-0030be1ea434)

5. **Reiniciar y verificar**
   - Reinicie el equipo.
   - Abra `cmd`, ejecute `systeminfo` y confirme que aparece la siguiente información:

     ```
     A hypervisor has not been detected. Features required for Hyper-V will not be displayed.
     ```

   ![Systeminfo Verification](https://github.com/user-attachments/assets/0dfb356f-c5ff-4f96-88ac-0a8f6f92768f)

---


