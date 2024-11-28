#include <stdio.h>
#include <string.h>
#include <stdlib.h>

int main()
{
    typedef struct player{
char name[20];
char team[20];
}player;

typedef struct bowl{
char type[10]; // seemer, pacer, spinner// N/A
char arm[5]; //left or right
player ply;
}bowl;

typedef struct bat{
char type[10]; // top order, middle order, lower order
char handed[8]; //lefty or righty
bowl ply2;
}batsman;


void createplayer(player *p){
    FILE *ptr=fopen("data.txt","a");
    if(ptr!=NULL){
        fprintf(ptr,"%s %s",p->name,p->team);
        fclose(ptr);
    }else{
        printf("Error!");
    }
}

void bowler(bowl *b){
     FILE *ptr=fopen("data.txt","a");
    if(ptr!=NULL){
        fprintf(ptr,"%s %s %s %s",b->type,b->arm,b->ply.name,b->ply.team);
        fclose(ptr);
    }else{
        printf("Error!");
    }
}

void bat(batsman *v){
    FILE *ptr = fopen("data.txt", "a");
    if (file != NULL) {
        fprintf(ptr, "%s %s %s %s %s %s,
                v->type, v->handed, v->ply2.type, v->ply2.arm, v->ply2.ply.name, v->ply2.ply.team);
        fclose(ptr);
    } else {
        printf("Error!");
    }
}

void readall(){
    FILE *ptr=fopen("data.txt","r");
    char line[1000000];
    if(ptr!=NULL){
        while(fgets(line,sizeof(line),ptr)){
            printf("%s",line);
        }fclose(ptr);
        
    }else{
        printf("Error");
    }
}
void updatePlayer(char *name, char *newTeam) {
    FILE *ptr = fopen("data.txt", "r+");
    char line[256];
    int found = 0;
    while (fgets(line, sizeof(line), ptr)) {
        if (strstr(line, name)) {
            found = 1;
            fseek(file, -strlen(line), SEEK_CUR);
            fprintf(file, "Player: %s, Team: %s\n", name, newTeam);
            break;
        }
    }
    if(found==0){
        printf("Not found");
    }
    fclose(file);
    return;
}
void deletePlayer(char *name) {
    FILE *ptr = fopen("data.txt", "r");
    FILE *tempFile = fopen("temp.txt", "w");
    char line[256];
    int found = 0;
    
    if (ptr != NULL && tempFile != NULL) {
        while (fgets(line, sizeof(line), ptr)) {
            if (strstr(line, name)) {
                found = 1; 
                continue;
            }
            fputs(line, tempFile);
        }
        fclose(ptr);
        fclose(tempFile);

        if (found) {
            remove(data.txt);
            rename("temp.txt", data.txt);
        } else {
            remove("temp.txt");
            printf("error");
        }
    } else {
        printf("Error opening file.\n");
    }
}
int main(){
    player p1={"Babar","Pakistan"};
    bowl b1={"Fast","right",{"Babar","Pakistan"}};
    bat b2={"Top Order","righty",{"Fast","right",{"Babar","Pakistan"}}};
    createplayer(&p1);
    bolwer(&b1);
    bat(&b2);
    readall();
    deletePlayer();
    updatePlayer();
    
    
    return 0;
}
}
