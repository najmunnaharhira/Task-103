% Define the equation you want to find the root of
function y = equation(x)
    y = x^3 - 4*x^2 + 2*x + 1;
end

% False-Position method to find the root of the equation
function roots = false_position_method(equation, a, b, tolerance, max_iterations)
    roots = zeros(1, max_iterations);
    for i = 1:max_iterations
        fa = equation(a);
        fb = equation(b);
        c = b - (fb * (b - a)) / (fb - fa);
        roots(i) = c;
        if equation(c) == 0 || abs(b - a) < tolerance
            break;
        end
        if sign(equation(c)) == sign(fa)
            a = c;
        else
            b = c;
        end
    end
    roots = roots(1:i); % Trim unused elements
end

% Initial interval [a, b], tolerance, and maximum number of iterations
a = -3;
b = 3;
tolerance = 1e-6;
max_iterations = 50;

% Find roots using the False-Position method
roots = false_position_method(@equation, a, b, tolerance, max_iterations);

% Plot the equation and the roots
x = linspace(a, b, 400);
y = arrayfun(@equation, x);
plot(x, y, 'b', 'LineWidth', 1.5);
hold on;
plot(roots, zeros(1, length(roots)), 'ro', 'MarkerSize', 8);
title('False-Position Method for Root Finding');
xlabel('x');
ylabel('y');
grid on;
legend('Equation', 'Roots');
