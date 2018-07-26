#Compiler setting
CC=				g++
CFLAGS=			-c -Wall
GLFLAGS=		-lGL -lGLU -lglut
SDLFLAGS=		-lSDL -lSL_image
#File name setting
CODE=			springSimulation.cpp
#Bullet3 libraries and headers addresses
B3BINFOLDER=	~/Bullet/bullet3/bin
B3BUILDSUFFIX=	_gmake_x64_release
B3SOURCE=		~/Bullet/bullet3/src/
#Bullet3 libraries
B3SB=			$(B3BINFOLDER)/libBulletSoftBody$(B3BUILDSUFFIX).a
B3D=			$(B3BINFOLDER)/libBulletDynamics$(B3BUILDSUFFIX).a $(B3BINFOLDER)/libBullet3Dynamics$(B3BUILDSUFFIX).a
B3C=			$(B3BINFOLDER)/libBulletCollision$(B3BUILDSUFFIX).a $(B3BINFOLDER)/libBullet3Collision$(B3BUILDSUFFIX).a
B3LM=			$(B3BINFOLDER)/libLinearMath$(B3BUILDSUFFIX).a
B3FILELOADER=	$(B3BINFOLDER)/libBullet2FileLoader$(B3BUILDSUFFIX).a
B3OPENCL=		$(B3BINFOLDER)/libBullet3OpenCL_clew$(B3BUILDSUFFIX).a
#Bullet2 libraries and headers addresses
B2PATH=			~/Bullet/bullet-2.82
B2SOURCE=		$(B2PATH)/src/
B2SB=			$(B2PATH)/lib/libBulletSoftBody.a
B2D=			$(B2PATH)/lib/libBulletDynamics.a
B2C=			$(B2PATH)/lib/libBulletCollision.a
B2LM=			$(B2PATH)/lib/libLinearMath.a
#Output setting
OUTPUT=			output.out
EXECUTE=		./$(OUTPUT)
TEXTOUTPUT=		output.txt


bullet3: $(CODE)
	@ $(CC) $(CODE) -I $(B3SOURCE) $(B3D) $(B3C) $(B3LM) -o $(OUTPUT)

bullet2: $(CODE)
	@ $(CC) $(CODE) -I $(B2SOURCE) $(B2D) $(B2C) $(B2LM) -o $(OUTPUT)

run: $(OUTPUT)
	@ $(EXECUTE)

clean: 
	@ rm *.out *.o *.txt

write: $(OUTPUT)
	@ $(EXECUTE)>$(TEXTOUTPUT) && libreoffice --calc $(TEXTOUTPUT)

profile: $(OUTPUT)
	@ valgrind $(EXECUTE)