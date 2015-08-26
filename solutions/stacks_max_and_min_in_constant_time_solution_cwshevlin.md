#### Pseudocode:

```
class MaxAndMinStack

  def init
    @max = Stack.new # A normal vanilla stack, not the class we are presently writing. We'll pretend like we're borrowing this from out previous exercise.
    @min = Stack.new
    @store = Stack.new
  end

  def push(int)
    push_check_max(int)
    push_check_min(int)
    @store.push(int)
  end

  def pop
    pop_check_max
    pop_check_min
    @store.pop
  end

  def peek
    @store.peek
  end

  def is_empty?
    @store.is_empty?
  end

  private

    def push_check_max(int)
      if int >= @max.peek # Using greater than or equal to so that we can keep track if multiple integers of equal value are pushed on the stack, then popped off the stack, or if max and min are the same. You could do it without including equal.
        @max.push(int)
      end
    end

    def push_check_min(int)
      if int <= @min.peek
        @min.push(int)
      end
    end

    def pop_check_max
      if @store.peek == @max.peek
        @max.pop
      end
    end

    def pop_check_min
      if @store.peek == @min.peek
        @min.pop
      end
    end

end
```
