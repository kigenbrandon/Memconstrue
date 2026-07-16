ASM = nasm
SRC_DIR = src
BUILD_DIR = build

# Default target
all: $(BUILD_DIR)/main_floppy.img

# Rule to create the floppy image
# FIX: Depend on $(BUILD_DIR)/main.bin, NOT $(SRC_DIR)/main.bin
$(BUILD_DIR)/main_floppy.img: $(BUILD_DIR)/main.bin
	cp $< $@
	truncate -s 1440k $@

# Rule to compile the assembly
$(BUILD_DIR)/main.bin: $(SRC_DIR)/main.asm
	@mkdir -p $(BUILD_DIR)
	$(ASM) -f bin -o $@ $<

clean:
	rm -rf $(BUILD_DIR)   