ASM = nasm
SRC_DIR = ../src
BUILD_DIR = .
BIN = $(BUILD_DIR)/main.bin
IMG = $(BUILD_DIR)/main_floppy.img
SRC = $(SRC_DIR)/main.asm

all: $(IMG)

$(IMG): $(BIN)
	powershell -NoProfile -Command "$src = '$(BIN)'; $dst = '$(IMG)'; Copy-Item $src $dst -Force; $fs = [System.IO.File]::Open($dst, [System.IO.FileMode]::OpenOrCreate); $fs.SetLength(1440 * 1024); $fs.Close()"

$(BIN): $(SRC)
	$(ASM) -f bin -o $(BIN) $(SRC)

clean:
	powershell -NoProfile -Command "Remove-Item '$(BIN)' -ErrorAction SilentlyContinue; Remove-Item '$(IMG)' -ErrorAction SilentlyContinue"

.PHONY: all clean