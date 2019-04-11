#./src/Makefile
OBJ = facedetectcnn.o
OBJ += facedetectcnn-floatdata.o
OBJ += facedetectcnn-int8data.o 
OBJ += facedetectcnn-model.o  
 #添加需要的文件就行，类似内核编译那种

$(OBJ):$(OBJ:.o=.cpp)
	$(CC) -c $^

clean:
	-rm $(OBJ)