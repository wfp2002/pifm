# pifm

Apenas clonar executar o chmox +x pifm, e colocar a antena no GPIO4 Pino 7 do Raspberry

Para executar: ./pifm arquivo_wav frequencia sample_rate

Exemplo: sudo ./pifm audio.wav 100.6 48000

Transmitindo com minimodem:

while true; do echo -e "mensagem" | minimodem -t rtty -f /tmp/file.wav && sudo ./pifm /tmp/file.wav 100.6 48000; sleep 10; done

Esse comando envia a mensagem a cada 10 segundos via pifm

Para recepcionar usando um radio FM plugado na entrada de som na outra ponta digite:

sudo arecord -f S16_LE -r 48000 -Dplughw:0 - | minimodem -r rtty -R 48000 -f -

No caso da opcao -Dplughw:0 pode ser :1 tambem depende da placa de som, para verificar digite aplay -l ou aplay -L
