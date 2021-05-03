

# Space war game!

mutable struct Position
    x::Int
    y::Int
end

struct Size
    width::Int
    height::Int
end

struct Widget
    name::String
    position::Position
    size::Size
end


# functions

# single-line functions
move_up!(widget, v)    = widget.position.y -= v
move_down!(widget, v)  = widget.position.y += v
move_left!(widget, v)  = widget.position.x -= v
move_right!(widget, v) = widget.position.x += v


# Typed arguments

# long version

# function move_up!(widget, v)
#     widget.position.y -= v
# end


# Annotating function arguments

#redefine move_up!
move_up!(widget::Widget, v::Int)= widget.position.y -= v



#show functions:
# Define pretty print functions
Base.show(io::IO, p::Position) = print(io, "(", p.x, ",", p.y, ")")
Base.show(io::IO, s::Size) = print(io, s.width, " x ", s.height)
Base.show(io::IO, w::Widget) = print(io, w.name, " at ", w.position, " size ", w.size)


# let's test these functions
w = Widget("asteroid", Position(0, 0), Size(10, 20))
move_up!(w, 10)
move_down!(w, 10)
move_left!(w, 20)
move_right!(w, 20)

# should be back to position (0,0)
print(w)


# Make a bunch of asteroids
function make_asteroids(N::Int, pos_range = 0:200, size_range = 10:30)
    pos_rand() = rand(pos_range)
    sz_rand() = rand(size_range)
    return [Widget("Asteroid #$i",
                Position(pos_rand(), pos_rand()),
                Size(sz_rand(), sz_rand()))
        for i in 1:N]
end
