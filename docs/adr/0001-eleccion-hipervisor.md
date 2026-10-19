# ADR 0001 — Elección de hipervisor

## Estado
Aceptado

## Contexto
Necesitamos un hipervisor para ejecutar 5 VMs (Windows Server,
Linux, SMB, backups, monitorización) en un único host físico
con recursos limitados.

En la presentación inicial se mencionó VMware, pero la arquitectura
mostrada usa Proxmox VE. Hay que decidir uno.

## Decisión
Usar **Proxmox VE** como hipervisor principal.

## Justificación
- Open source y gratuito (VMware exige licencias).
- Interfaz web integrada para gestionar VMs, snapshots y backups.
- Basado en KVM + LXC, buen rendimiento con recursos limitados.
- Comunidad activa y documentación abundante.
- Permite contenedores LXC para servicios ligeros (ahorro de RAM).

## Consecuencias
- Hay que aprender la interfaz de Proxmox (curva baja).
- Los backups se pueden hacer con Proxmox Backup Server.
