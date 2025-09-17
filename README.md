# Projeto Servo

Este projeto é um exemplo de controle de servo motor utilizando Raspberry Pi Pico e o SDK Pico.

## Estrutura do Projeto
- `servo.c`: Código fonte principal do controle do servo.
- `CMakeLists.txt`: Script de build para CMake.
- `pico_sdk_import.cmake`: Importação do SDK Pico.
- `build/`: Diretório gerado pelo CMake contendo arquivos de build e binários.

## Requisitos
- Raspberry Pi Pico
- SDK Pico instalado
- Ferramentas: CMake, Ninja, OpenOCD, Picotool

## Como Compilar
1. Configure o ambiente do SDK Pico.
2. Execute o comando de build:
   ```powershell
   ${env:USERPROFILE}/.pico-sdk/ninja/v1.12.1/ninja.exe -C build
   ```

## Como Gravar no Pico
1. Compile o projeto.
2. Use o Picotool para gravar o binário:
   ```powershell
   ${env:USERPROFILE}/.pico-sdk/picotool/2.2.0/picotool/picotool.exe load <caminho_para_binario> -fx
   ```

## Como Fazer Flash via OpenOCD
1. Compile o projeto.
2. Execute:
   ```powershell
   ${env:USERPROFILE}/.pico-sdk/openocd/0.12.0+dev/openocd.exe -s ${userHome}/.pico-sdk/openocd/0.12.0+dev/scripts -f interface/cmsis-dap.cfg -f target/<target>.cfg -c "adapter speed 5000; program '<caminho_para_binario>' verify reset exit"
   ```

## Licença
Este projeto está sob a licença MIT.
