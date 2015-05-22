# Little Book of Bugs
This book lists kinds of frequent bugs of a new programmer, and the target for the list is to remind people to avoid programmer 
resolve the same problem twice.

#Bug1

	char* buf = malloc(strlen(string));  /* BUG! */
	strcpy(buf, string);
  
This is unsafe because cstring.size(c++) or strlen(C) always return the length of "chararcters" without "null-terminator".
function strcpy always copy "null-terminator".

	/* Try this: */
	char* buf_for_string = malloc(strlen(string) + 1);
	strcpy(buf_for_string, string);
  
	int* buf_for_int = malloc(30);
	for (int i = 0; i<30; i++) {
		*(buf_for_int + i) = i;
	}
