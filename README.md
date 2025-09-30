#include <stdio.h>

int main() {
    FILE *fp;
    char data[100];

    // Open file for writing
    fp = fopen("sample.txt", "w");
    if (fp == NULL) {
        perror("Error opening file for writing");
        return 1;
    }
    fprintf(fp, "Hello, this is a file handling example.\n");
    fclose(fp);

    // Open file for reading
    fp = fopen("sample.txt", "r");
    if (fp == NULL) {
        perror("Error opening file for reading");
        return 1;
    }

    printf("File content:\n");
    while (fgets(data, sizeof(data), fp) != NULL) {
        printf("%s", data);
    }
    fclose(fp);

    return 0;
}
