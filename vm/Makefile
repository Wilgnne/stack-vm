# Location of the files
SRC = src
HEAD = include
OBJ_DIR = build
SOURCES = $(wildcard $(SRC)/*.c)
OBJECTS = $(patsubst $(SRC)/%.c, $(OBJ_DIR)/%.o, $(SOURCES))
HEADERS = $(wildcard $(HEAD)/*.h) $(wildcard $(GLOBAL_HEAD)/*.h)

PROJ_NAME = $(BIN_DIR)/ss-vm

vm: $(OBJECTS) $(HEADERS)
	@echo building the virtual machine
	@echo $(OBJECTS)
	$(CC) -o $(PROJ_NAME) $(OBJECTS)

$(OBJ_DIR)/%.o: $(SRC)/%.c
	@mkdir -p $(@D)
	$(CC) $(CFLAGS) -I$(SRC) -I$(HEAD) -I$(GLOBAL_HEAD) -c $< -o $@

.PHONY: clean
clean:
	@$(RM) -r -f $(OBJ_DIR)
	@echo "    Remove Objects:   $(OBJECTS)"
