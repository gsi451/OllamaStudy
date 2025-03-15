https://huggingface.co/yanolja/EEVE-Korean-Instruct-2.8B-v1.0/tree/main
이 자료를 ollama에 연동해 본 메뉴얼

1. ollama에서 바로 모델을 다운로드 받을수가 없어서 gguf를 수동으로 받아서 추가해야 한다.
2. ollama의 모델 폴더는 어디있지? 찾다 보니 명령어로 가능했다.
   - cd ~/.ollama
   - 이 명령어를 사용하니 나왔다. (/Users/sonbyeong-ug/.ollama)
4. 다운로드 받기
   - gguf rudfh : https://huggingface.co/heegyu/EEVE-Korean-Instruct-10.8B-v1.0-GGUF
  huggingface-cli download \
  heegyu/EEVE-Korean-Instruct-10.8B-v1.0-GGUF \
  ggml-model-Q4_K_M.gguf \
  --local-dir /Users/sonbyeong-ug/.ollama/models \
  --local-dir-use-symlinks False
6. vscode를 열어서 Modelfile을 작성
   - 다운로드 받은 폴더를 좀 정리를 하였다.
   - models 폴더 안에 EEVE-Korean-Instruct-10.8B-v1.0-GGUF/ggml-model-Q4_K_M.gguf 에 위치하도록 이동했다.
   - Modelfile 도 동일한 폴더에 추가했다.
8. 콘솔에서 명령어 실행
    -  ollama create EEVE-Korean-10.8B -f models/EEVE-Korean-Instruct-10.8B-v1.0-GGUF/Modelfile
    -  ollama list 실행하니 EEVE-Korean-10.8B:latest 이게 보아면 정상
10. ollama run EEVE-Korean-10.8B:latest 실행
