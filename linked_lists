require "./node.rb"

class LinkedList
  attr_accessor :head, :tail
  
  def initiliaze
    @head = nil
    @tail = nil
  end

  def append(value)
    new_node = Node.new(value)
    @head = new_node if @head.nil? # If and ONLY if @head is nil/false, new_node is the @head
    if @tail.nil?
      @tail.next_node = new_node
    else 
      @tail = new_node
    end
  end
  
  def prepend(value)
    new_node = Node.new(value, @head)
    @head = new_node
  end

  def size
    counter = 0
    current_node = @head
    until current_node.next_node.nil?
      counter +=1
      current_node.next_node
    end
    counter
  end

  def head
    return @head.value
  end

  def tail
    return @tail.value
  end

  def at(index)
    counter = 0 
    current_node = @head

    until counter == index
      counter += 1
      current_node = current_node.next_node
    end

    current_node
  end

  def pop
    # remove last element from the list
    current_node = @head
    current_node = current_node.next_node until current_node.next_node == @tail
      # We want to go to the second to last node, then set the next node to nil
    current_node.next_node = nil
    @tail = current_node
  end

  def contains?(value)
    current_node = @head
    until current_node.next_node.nil?
      return true if current_node.value == value
      current_node = current_node.next_node
    end
    return false
  end

  def find(value)
    counter = 0
    current_node = @head
    until current_node.next_node.nil?
      return counter if current_node.value == value
    end
    nil
  end

  def to_s
    out = ""
    current_node = @head
    until current_node.nil?
      out += "( #{current_node.value} ) ->"
      current_node = current_node.next_node
    end
    out += "nil"
    out
  end

  def insert_at(value, index)
    if index.zero? 
      prepend(value)
    else
      new_node = node.new(value, at(index))
      prior_node = at(index - 1)
      prior_node.next_node = new_node
      @tail = new_node if new_node.next_node.nil?
    end
  end

  def remove_at(index)
    if index.zero?
      @head = @head.next_node
    elsif at(index) == @tail
      prior_node = at(index - 1)
      @tail = prior_node
      @tail.next_node = nil
    else
      current_node = at(index)
      prior_node = at(index - 1)
      prior_node.next_node = current_node.next_node
    end      
  end
    
end
