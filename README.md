# Report for Assignment 1

## Project chosen
Name: Godot Engine

URL: https://github.com/godotengine/godot.git

Number of lines of code and the tool used to count it: 2326 KLOC, tested by lizard with command `lizard -l cpp`

Programming language: C++
## Coverage measurement

### Existing tool
name: OpenCppCoverage

The way it was executed: After the development version of Godot compile( enabling it to be tested and be with debugged symbols),
run OpenCppCoverage withe command line like this: OpenCppCoverage --  ./bin/godot.windows.editor.dev.x86_64.exe --test
the execuatable will run with all the tests and the OpenCppCoverage will check which part of the code is covered.

Because it is a really big project(it contains millions of lines of code), so we focus on the two specific part of the project which are camera_3d and node_2d, so we specificlly measure the coverage
of that part with OpenCppCoverage.

![image](https://github.com/SiyuanHong/godot/assets/113177812/0deb4c66-1d6c-424b-9388-72f9b2aac294)

![image](https://github.com/SiyuanHong/godot/assets/113177812/fac86148-feee-4f9d-af3e-a7e0d279e1c9)



### Your own coverage tool
Siyuan Hong

  Function 1

  name: set_global_rotation

  a link to the commit: https://github.com/godotengine/godot/commit/1f69989fd6d0913a7ab1e973b162d2c026b4a0fa

  screenshot:

i identified two branches in this function:

![image](https://github.com/SiyuanHong/godot/assets/113177812/e5eae959-3010-4213-b9df-abd98d97b057)


 here you can see they are not reached in the original test 

  Function 2

  name:Move_X

  a link to the commit: https://github.com/godotengine/godot/commit/1f69989fd6d0913a7ab1e973b162d2c026b4a0fa

  screenshot:

 i identified two branches in this function:

![image](https://github.com/SiyuanHong/godot/assets/113177812/20faae7f-c0a4-438a-8786-642b853397ab)


they are not reached in the original test.

Ruizhe Tao

Function 1

name: set_global_skew

a link to the commit: https://github.com/SiyuanHong/godot/commit/069884f925777869f8bf04b8f5257e045245dfa0

screenshot:

2 branches with unique ids are identified in this function:

![skew_uncovered](https://github.com/SiyuanHong/godot/assets/50838626/ba783274-4cb1-4709-b297-b55f52c24516)

Function 2

name: set_global_scale

a link to the commit: https://github.com/SiyuanHong/godot/commit/069884f925777869f8bf04b8f5257e045245dfa0

screenshot:

2 branches with unique ids are identified in this function:

![scale_uncovered](https://github.com/SiyuanHong/godot/assets/50838626/16a5f470-637e-423c-aed3-433ac9b14c95)

Rui Chen:

Function 1:

Name: 'set_environment'

Link to the commit: https://github.com/godotengine/godot/commit/7c6ba1300427b16f14dff541063ebf8962ca251d

Screenshot:
Two branches with unique IDs are identified in this function.
<img width="552" alt="environment_uncovered" src="https://github.com/SiyuanHong/godot/assets/117285044/b0a7fec9-82ff-4398-989e-ddb2e04422c8">

Function 2:

Name: 'set_composition'

Link to the commit: https://github.com/godotengine/godot/commit/7c6ba1300427b16f14dff541063ebf8962ca251d

Screenshot:
Two branches with unique IDs are identified in this function.
<img width="532" alt="compositor_uncovered" src="https://github.com/SiyuanHong/godot/assets/117285044/a0e6d918-67c4-4dea-8cba-290498c28c75">

Jiarui Pan

Function 1

Name: get_relative_transform_to_parent (https://github.com/SiyuanHong/godot/commit/71915e9fa0e7086a981b766665cf2fa0202d4bbe)

Screenshot:

<img width="947" alt="before test1" src="https://github.com/SiyuanHong/godot/assets/122408769/a44cd384-abae-4ff4-a188-7a402463c4df">

Four branches are identified as 0, 1, 2 and 3, contained by coverageDataOfPjrs. At this stage none of these branches are reached by the exisiting tests.

Function 2

Name: set_current (https://github.com/SiyuanHong/godot/commit/71915e9fa0e7086a981b766665cf2fa0202d4bbe)

Screenshot:

<img width="949" alt="before test2" src="https://github.com/SiyuanHong/godot/assets/122408769/bdc3c18c-001b-49ff-be9d-7450292753b8">

Three branches are identified as 0, 1 and 2. To seperate, container is differently named as coverageDataOfPjrs2. At this stage none of these branches are reached by the exisiting tests.

## Coverage improvement

### Individual tests
Siyuan Hong

test1:

a link to the commit:
    https://github.com/godotengine/godot/commit/ccfc99d5fcb0749b589d83237d67668e7a522451

old result:
     ![image](https://github.com/SiyuanHong/godot/assets/113177812/155ef51b-68f8-4375-871a-fd8d79333f9b)

new result:
     ![image](https://github.com/SiyuanHong/godot/assets/113177812/89324321-d88b-4e21-b945-26352c4365ce)


     the coverage improved by 100%.

     comment: because previously, this function is not covered by any tese case, so i just write a new test case to set one node with a rotation degree and see how does that function works.
     the condition branches include node with a parent node and without parent node, so i just write a parent node and childe node attached to it, and call set_global_rotation separately,
     then all the three branches are reached.

test2:

a link to the commit:
     https://github.com/godotengine/godot/commit/ccfc99d5fcb0749b589d83237d67668e7a522451

old result:
     ![image](https://github.com/SiyuanHong/godot/assets/113177812/1044a01c-5e7c-43e7-8da4-2e9ca6d3beea)


new result:
     ![image](https://github.com/SiyuanHong/godot/assets/113177812/5ea315a2-2ac6-4886-9d8d-36d895f2ba54)


     the coverage improved by 100%

     comment: because previously, this function is not covered by any tese case, now i write a new test case which set the second argument as true first to skip if conidtions path first and 
     then set it as false to enter this conditional path. 

Ruizhe Tao

Test 1

a link to the commit: https://github.com/SiyuanHong/godot/commit/069884f925777869f8bf04b8f5257e045245dfa0

old result: \
![skew_uncovered](https://github.com/SiyuanHong/godot/assets/50838626/f43d6649-cc66-4220-b24e-f156599bae2f)

new result: \
![skew_covered](https://github.com/SiyuanHong/godot/assets/50838626/1246d93a-3152-492f-9b5c-6e02c5ce0a49)

	The coverage improved by 100%.
 	Since this function is not tested in the original project, a new test dedicated to this function was made.
  	By creating two nodes, parent node and child node, and assign the child node as the child of the parent node.
   	Use these two node objects to invoke `set_global_skew` function, both branches will be reached, as the condition
	checks if the node has a parent node.

Test 2

a link to the commit: https://github.com/SiyuanHong/godot/commit/069884f925777869f8bf04b8f5257e045245dfa0

old result: \
![scale_uncovered](https://github.com/SiyuanHong/godot/assets/50838626/7fa8a1b2-9d23-432d-8418-6e8a94b9f457)

new result: \
![scale_covered](https://github.com/SiyuanHong/godot/assets/50838626/db7ec6c7-885c-4d2c-8153-be25b8cee24b)

	The coverage improved by 100%.
 	This function is very similar to the previous one, and it is also not tested in the original project. A new test
  	dedicated to this function was made.
  	By creating two nodes, parent node and child node, and assign the child node as the child of the parent node.
   	Use these two node objects to invoke `set_global_scale` function, both branches will be reached, as the condition
	checks if the node has a parent node.

Rui Chen:

Test 1:

a link to the commit: https://github.com/godotengine/godot/commit/7c6ba1300427b16f14dff541063ebf8962ca251d

old result: \
<img width="552" alt="environment_uncovered" src="https://github.com/SiyuanHong/godot/assets/117285044/b0a7fec9-82ff-4398-989e-ddb2e04422c8">

new result: \
<img width="673" alt="environment_compositor_covered" src="https://github.com/SiyuanHong/godot/assets/117285044/e4d008e1-4521-4fc9-b00c-2914bc205310">

    The coverage improved by 100%.
    This function was not tested in orginal project, therefore, a new test is designed for this function.
    In the test case, both branch condition are reached. For the first branch, an new environment object was created and set. For the second branch, a NULL was set to meet the else case. `CHECK` is done on each condition.

Test 2:

a link to the commit: https://github.com/godotengine/godot/commit/7c6ba1300427b16f14dff541063ebf8962ca251d

old result: \
<img width="532" alt="compositor_uncovered" src="https://github.com/SiyuanHong/godot/assets/117285044/ec8baaa5-62f7-4efc-a1de-f5d4c27c16b6">

new result: \
<img width="673" alt="environment_compositor_covered" src="https://github.com/SiyuanHong/godot/assets/117285044/48666509-1fab-4f72-8613-9bc9c6df1c22">

    The coverage improved by 100%.
    This function was not testeed in orginal project, therefore, a new test is designed for this function.
    In the test case, both branch condition are reached. For the first branch, an new compositor object was created and set. For the second branch, to  set an invalid compositor object, I chose to create an 	compositor_effect. CHECK is done on each condition.

Jiarui Pan

Test1

a link to the commit: https://github.com/SiyuanHong/godot/commit/71915e9fa0e7086a981b766665cf2fa0202d4bbe

old results:

<img width="947" alt="before test1" src="https://github.com/SiyuanHong/godot/assets/122408769/982ab190-1d7e-44df-bc20-4976de5cbda4">

new result:

<img width="949" alt="after test1" src="https://github.com/SiyuanHong/godot/assets/122408769/cc312b04-de38-48d0-828a-5429ddc1f296">

     The coverage improved by 100%.

     Comment: Initially, no tests are responsible for this function, so a new testcase is created. According to the code, three cases diverge, thus, the testcase consists of three subcases: p_parent == this, p_parent == parent_2d and the rest. For each condition, content of the tests differs: for the first one, check if the transform by get_relative_transform_to_parent(node) returns the same as Transform2D() when p_parent is the node itself; for the second one, by linking the node to its parent node, check if the transform of the parent node is the same as child node; similarly, for the third one, by linking the node to its parent node and its grandparent node, check if the total transform of the node and its parent node is the same as the grandparent node. By do these, all branches are reached by the tests and coverage is improved.

Test2

a link to the commit: https://github.com/SiyuanHong/godot/commit/71915e9fa0e7086a981b766665cf2fa0202d4bbe

old results:

<img width="949" alt="before test2" src="https://github.com/SiyuanHong/godot/assets/122408769/cba6be7d-5b84-4596-8b2d-2c1d71ef0ef1">

new result:

<img width="904" alt="after test2" src="https://github.com/SiyuanHong/godot/assets/122408769/585bacde-f216-40e6-836e-e22d8b4850d5">

     The coverage improved by 100%.

     Comment: Initially, no tests are responsible for this function, so a new testcase is created. According to the code, two cases diverge, thus, the testcase consists of two subcases: when p_enabled and else. For the first condition, when set_current is true, the test checks if the function together with make_current are called while clear_current is not; likewise, the second subcase checks if the function together with clear_current are called while make_current is not. By do these, all branches are reached by the tests and coverage is improved.

### Overall
The old two parts: 

![image](https://github.com/SiyuanHong/godot/assets/113177812/0deb4c66-1d6c-424b-9388-72f9b2aac294)

![image](https://github.com/SiyuanHong/godot/assets/113177812/fac86148-feee-4f9d-af3e-a7e0d279e1c9)

The new two: 

![image](https://github.com/SiyuanHong/godot/assets/113177812/4eb4520b-573d-4769-8f83-2c5c5e0bc135)

![image](https://github.com/SiyuanHong/godot/assets/113177812/e85c2900-fd5e-45c0-a3fe-a522827068b5)



## Statement of individual contributions
Siyuan Hong: write function instrumentation for `set_global_rotation` and `move_x`, and implement tests for these two functions to cover all branches

Ruizhe Tao: write function instrumentation for `set_global_skew` and `set_global_scale`, and implement tests for these two functions to cover all branches

Rui Chen: write function instrumentation for `set_environment` and `set_compositor` and implement tests for these two functions to cover all branches

Jiarui Pan: write function instrumentation for `get_relative_transform_to_parent` and `set_current` and implement tests for these two functions to cover all branches
