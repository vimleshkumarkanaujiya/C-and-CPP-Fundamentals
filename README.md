# C-and-CPP-Fundamentals

<h3>How to initialize structure members?</h3>
Structure members cannot be initialized with declaration. For example, the following C program fails in the compilation.
<hr>
<code>
struct Point
{
int x = 0; // COMPILER ERROR: cannot initialize members here
int y = 0; // COMPILER ERROR: cannot initialize members here
};
</code>
<hr>

The reason for above error is simple, when a datatype is declared, no memory is allocated for it. Memory is allocated only when variables are created.
Structure members can be initialized using curly braces ‘{}’. For example, the following is a valid initialization.
<hr>
<code>
struct Point
{
int x, y;
};

int main()
{
// A valid initialization. member x gets value 0 and y
// gets value 1. The order of declaration is followed.
struct Point p1 = {0, 1};
}
</code>
<hr>

How to access structure elements? 
Structure members are accessed using dot (.) operator.
<hr>
<code>
#include <stdio.h>

struct Point {
	int x, y;
};
</code>
<code>
int main()
{
	struct Point p1 = { 0, 1 };

	// Accessing members of point p1
	p1.x = 20;
	printf("x = %d, y = %d", p1.x, p1.y);

	return 0;
}
</code>
<hr>
What is a structure pointer? 
Like primitive types, we can have a pointer to a structure. If we have a pointer to structure, members are accessed using arrow ( -> ) operator.
<hr>
<code>
#include <stdio.h>

struct Point {
	int x, y;
};
</code>
<code>
int main()
{
	struct Point p1 = { 1, 2 };

	// p2 is a pointer to structure p1
	struct Point* p2 = &p1;

	// Accessing structure members using structure pointer
	printf("%d %d", p2->x, p2->y);
	return 0;
}
</code>

