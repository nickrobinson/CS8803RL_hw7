Input:
int numStates = 12;
int numActions = 4;

double[][][] probabilitiesOfTransitions = {{{1.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{1.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{1.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{1.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0}},

{{0.0,0.1,0.8,0.0,0.0,0.1,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.9,0.1,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.9,0.0,0.0,0.0,0.1,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.1,0.1,0.0,0.0,0.8,0.0,0.0,0.0,0.0,0.0,0.0}},

{{0.0,0.0,0.9,0.0,0.0,0.0,0.1,0.0,0.0,0.0,0.0,0.0},
{0.0,0.1,0.9,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.8,0.1,0.0,0.0,0.0,0.1,0.0,0.0,0.0,0.0,0.0},
{0.0,0.1,0.1,0.0,0.0,0.0,0.8,0.0,0.0,0.0,0.0,0.0}},

{{0.0,0.0,0.0,1.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,1.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,1.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,1.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0}},

{{0.0,0.0,0.0,0.0,1.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,1.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,1.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,1.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0}},

{{0.0,0.1,0.0,0.0,0.0,0.0,0.8,0.0,0.0,0.1,0.0,0.0},
{0.0,0.8,0.0,0.0,0.1,0.0,0.1,0.0,0.0,0.0,0.0,0.0},
{0.0,0.1,0.0,0.0,0.8,0.0,0.0,0.0,0.0,0.1,0.0,0.0},
{0.0,0.0,0.0,0.0,0.1,0.0,0.1,0.0,0.0,0.8,0.0,0.0}},

{{0.0,0.0,0.1,0.0,0.0,0.0,0.0,0.8,0.0,0.0,0.1,0.0},
{0.0,0.0,0.8,0.0,0.0,0.1,0.0,0.1,0.0,0.0,0.0,0.0},
{0.0,0.0,0.1,0.0,0.0,0.8,0.0,0.0,0.0,0.0,0.1,0.0},
{0.0,0.0,0.0,0.0,0.0,0.1,0.0,0.1,0.0,0.0,0.8,0.0}},

{{0.0,0.0,0.0,0.0,0.0,0.0,0.0,1.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,1.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,1.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,1.0,0.0,0.0,0.0,0.0}},

{{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,1.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,1.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,1.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,1.0,0.0,0.0,0.0}},

{{0.0,0.0,0.0,0.0,0.0,0.1,0.0,0.0,0.0,0.1,0.8,0.0},
{0.0,0.0,0.0,0.0,0.0,0.8,0.0,0.0,0.0,0.1,0.1,0.0},
{0.0,0.0,0.0,0.0,0.0,0.1,0.0,0.0,0.0,0.9,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.9,0.1,0.0}},

{{0.0,0.0,0.0,0.0,0.0,0.0,0.1,0.0,0.0,0.0,0.9,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.8,0.0,0.0,0.1,0.1,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.1,0.0,0.0,0.8,0.1,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.1,0.9,0.0}},

{{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,1.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,1.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,1.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,1.0}}};

double[][][] rewards = {{{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0}},

{{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1},
{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1},
{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1},
{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1}},

{{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1},
{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1},
{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1},
{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1}},

{{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0}},

{{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0}},

{{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1},
{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1},
{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1},
{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1}},

{{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1},
{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1},
{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1},
{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1}},

{{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0}},

{{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0}},

{{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1},
{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1},
{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1},
{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1}},

{{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1},
{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1},
{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1},
{-0.1,-0.1,-0.1,-0.1,1.0,-0.1,-0.1,-1.0,-0.1,-0.1,-0.1,-0.1}},

{{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0},
{0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0}}};

double gamma = 0.99;

Output:
0.0, 0.783930008216784, 0.662924766337808, 0.0, 0.0, 0.9352181416696109, 0.7719518719957031, 0.0, 0.0, 0.7839313909844094, 0.6629264489131552, 0.0