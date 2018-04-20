# =============================================
# make 設置
# =============================================
CC=g++
CFLAGS=-O3 -std=c++14
INCPATH=\
-I./LapBlend\
-I./Raw2Img

SRC:=$(wildcard *.cpp ./LapBlend/*.cpp ./Raw2Img/*.cpp)
OBJ:=$(patsubst %.cpp,%.o,$(notdir $(SRC)))
# =============================================
# make 預設執行
# =============================================
resule: main.exe
	./main.exe

# =============================================
# 編譯檔案命令 [tag:cmd]
# =============================================
# 連結所有編譯後的檔案產生可執行檔
main.exe: $(OBJ)
	$(CC) $(CFLAGS) *.o -o main.exe

# 編譯所有cpp檔案
LapBlend_main.o:LapBlend_main.cpp
	$(CC) $(CFLAGS) $(INCPATH) -c LapBlend_main.cpp

LapBlend.o:$(wildcard ./LapBlend/*.*)
	$(CC) $(CFLAGS) $(INCPATH) -c ./LapBlend/LapBlend.cpp
Raw2Img.o:$(wildcard ./Raw2Img/*.*)
	$(CC) $(CFLAGS) $(INCPATH) -c ./Raw2Img/Raw2Img.cpp

# =============================================
# 命令列
# =============================================
# 清理所有編譯的檔案
clean:
	rm -f *.o main.exe
clean_o:
	rm -f *.o main.exe
# 編譯程式碼並執行
test:main.exe
	./main.exe
# 僅編譯出可執行檔，並清除緩存
all: main.exe  clean_o
	
# =============================================