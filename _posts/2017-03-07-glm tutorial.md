---
layout: post
title: glm tutorial
categories:
- 科教
tags:
- 科技
---
  <!--more-->

```C
#include <glm/vec3.hpp> // glm::vec3
#include <glm/vec4.hpp> // glm::vec4
#include <glm/mat4x4.hpp> // glm::mat4

#include <glm/gtc/type_ptr.hpp>    //glm::value_ptr
#include <glm/gtc/matrix_transform.hpp> // glm::translate, glm::rotate, glm::scale, glm::perspective

using namespace glm;
glm::mat4 Projection = glm::perspective(glm::radians(45.0f), 4.0f / 3.0f, 0.1f, 100.f);
mat4 projection = ortho(0.0f, 1.0f, 0.0f, 1.0f);
mat4 translate = translate(mat4(1.0f), vec3(0.5f, 0.5f, 0.0f));
mat4 rotate = rotate(mat4(1.0f), 90.0f, vec3(0.0f, 0.0f, 1.0f));
mat4 scale = scale(mat4(1.0f), vec3(0.5f, 0.5f, 1.0f));
mat4 m = translate * scale * rotate;// must be scale * rotate * translate

mat n= inverse(m); //transpose(m);


glm::vec4 Position = glm::vec4(glm::vec3(0.0), 1.0);
glm::mat4 Model = glm::mat4(1.0);    // construct identity matrix
Model[4] = glm::vec4(1.0, 1.0, 0.0, 1.0);
glm::vec4 Transformed = Model * Position;

// column 
m4[0]     // column zero
m4[0].x   // same as m4[ 0 ][ 0 ]
m4[0].y   // same as m4[ 0 ][ 1 ]
m4[0].z   // same as m4[ 0 ][ 2 ]
m4[0].w   // same as m4[ 0 ][ 3 ]

myz[1][1] = -1; myz[2][2] = -1;

float aaa[16];
glm::mat4 bbb = glm::make_mat4(aaa);

glm::mat4 bbb;
memcpy(glm::value_ptr(bbb), aaa, sizeof(aaa));

glm::value_ptr(m4)    is same as     &m4[0][0]

```
