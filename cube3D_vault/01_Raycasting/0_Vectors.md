Vectors are mathematical objects that are able to represent quantities that have both magnitude and direction. In our code, it can be represented as :
```
typedef struct s_vector
{
	long       x;
	long       y;
}              t_vector;
```
Lets not forget that our coordinates system will have the y axis reversed from the traditional cartesian coordinates system.

We will use vectors a lot in our code to store positions and directions.

There are a lot of functions needed to correctly interact with such objects, and here's the list of the basics handling:

- `char *vec_to_str(const t_vector *vec);`
This function will put a vector as a string, to facilitate debugging.
The string shall be formatted this way : `(<x>,<y>)`

- `double vec_len(const t_vector *vec);`
This function will return the length (or magnitude) of the vector as a scalar.

- `double vec_len_sqrd(const t_vector *vec);`
This function will return the length (or magnitude) of the vector as a scalar. This should be faster since calculating square roots is expensive, but idk yet if this function will find a use in spher4d.

- `t_vector vec_invert(const t_vector *vec);`
This function simply inverts the given vector, which equates to multiplying its x and y values by -1.

- vector operations :
  - `t_vector vec_add(const t_vector *vec1, const t_vector *vec2);`
  - `t_vector vec_sub(const t_vector *vec1, const t_vector *vec2);`
  - `t_vector vec_mult(const t_vector *vec, double multiplier);`
  - `t_vector vec_div(const t_vector *vec, double divisor);`

- `double vec_angle(const t_vector *vec);`
This function returns the angle of the vector compared to the x axis.

- `double vec_dot_product(const t_vector *vec1, const t_vector *vec2);`
 The dot product of two vectors is a scalar value. If the dot product is positive, the angle is less than 90 degrees, indicating that the vectors are pointing in a generally similar direction. A negative dot product means the angle is greater than 90 degrees, showing that the vectors are pointing in generally opposite directions. If the dot product is zero, the vectors are perpendicular.

- `double vec_angle_between(const t_vector *vec1, const t_vector *vec2);`
This function return a double indicating the degrees between vec1 and vec2.