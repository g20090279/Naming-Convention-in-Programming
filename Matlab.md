# Naming Convention in Matlab

## Variables

Variables in Matlab can not begin with a number, and contain **spaces**, **#**, **$**, **%**, **&**, and so on.

As other programming languages recommended, a good name should be self-descriptive. Many name variable with **camelCase**.

```matlab
% Variable representing the number of objects, 'n' as prefix
nHours = 60;    % number of Hours
nIter  = 1000;  % number of iteration

% The uppercase acronyms should be written in mixed or lower case
% bad
nTXAnt = 64;
% good
nTxAnt = 64;    % number of transmitter antennas

% A constant is in uppercase. If multiples words, they are connected with underscore.
NUM_TX          = 64;
SPEED_LIGHT     = 3e8;
MAX_ITERATION   = 1000;
THRESHOLD       = 10;

% Iterator variables use 'i', 'j', or 'k' as prefix
for iIter = 1:nIter
    %<to do>
end

% Boolean with 'is' as prefix
isChecked = false;

% Do not name a variable with default keywords, and functions with default functions
% bad
function length()
    %<to do>
end
% good
function lengthArray()
    %<to do>
end

% Structure variables are named with a capital letter in the beginning
Codebook = struct ();
```

Having two variables with names differing only by a final letter s
should be avoided. We decide in the beginning before coding if we name all variables in **singular** or **plural**.

## Functions

The functions originated from The MathWorks are in **lower case**, say `meshgrid`, `polarplot`, `linspace`.

In other languages, functions are also usually declared with **camelCase**. Few may use **snake_case**, which is not common. The first word is usually set to a verb, such as **generate**, **calculate**, **compute**, **find**, **initialize**, **check**, **get/set**, **add/remove**, **create/destory**, **suspend/resume**, **show/hide** etc., to describe what the function is doing.

```matlab
% bad
function compute_sinr ()
    %<to do>
end

% good
function computeSinr ()
    %<to do>
end

% good 
function computeChannelResponse ()
    %<to do>
end

% Initialization Function
% bad
function initProblemState ()
    %<to do>
end
% good
function initializeProblemState ()
    %<to do>
end

% Boolean Function with prefix 'is', or 'has', 'can', 'should'
function isRecieved ()
    %<to do>
end
```

The constants that are output by a function with the same name should be in **lowercase** or **camelCase**. For example, `pi` is a built-in function in Matlab, and the output is `pi` in lowercase.

## Class

**Class** as well as its **properties** in Matlab are named with **PascalCase**.

```matlab
% Officical Definition of Class, Methods and Functions in Matlab
classdef ClassName
    properties
        PropertyName
    end
    methods
        function obj=ClassName(arg1,...)
            obj.PropertyName = arg1;
            ...
        end
        function ordinaryMethod(obj,arg1,...)
            ...
        end
    end
    methods (Static)
        function staticMethod(arg1,...)
            ...
        end
    end
end
```