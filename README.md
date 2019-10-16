#### I have not idea what I am doing, please help me fix my code! I seem to have made some mistakes.

```ruby
class Document
   attr_accessor :content, :title

  def initialize
    @content = content
    @title = title
  end

  def to_s
    "#{title}: #{content}"
  end
end

doc = Document.new
doc.title = "Ruby Exam"
doc.content = "TODO some questions"

puts doc.title
puts doc.content
puts doc
```

#### I made a mistake in the RubyExam, can you find it?

```ruby
class RubyExam
  def initialize
    @score = 0
    @current_question = 1
  end

  def got_one_right
    @score+=1
    self.next
  end

  def got_one_wrong
    self.next
  end

  def next
    @current_question+=1
  end

  def redo
    puts "I made no mistake!"
    @score = 10
  end
  
  def complete
    if @score < 10
      puts 'Game Over'
    else
      self.redo
    end
    puts "Final Score: #{@score}"
  end
end

exam = RubyExam.new
exam.got_one_right
exam.got_one_wrong
exam.got_one_wrong
exam.complete
```

#### What are 3 ways to create a new Hash?

- Hash.new()
- h = {"k" => "v"}
- h = {"k":"v"}

#### Which of the following are valid for __X__?

```ruby
def save!(array)
  raise ArgumentError.new('arg should be array') unless array.is_a?(Array)

  # do stuff ..
rescue ArgumentError => e
  puts 'Failed to save!'
  puts $1
  puts $1.message
  puts $1.backtrace
  puts $@
end
```

- [ ] `Error => e`
- [x] *nothing*
- [ ] `SystemError => e`
- [x] `ArgumentError => e`
- [x] `StandardError => e`
- [x] `ArgumentError`
- [ ] ` => ArgumentError`
- [ ] ` => argument_error`

#### What is the correct output for:

```ruby
d = Date.parse('01-02-99') << 1
p d.to_s
```

- [ ] `"1999-01-02"`
- [ ] `"1998-01-01"`
- [ ] `"1998-12-31"`
- [ ] `"1998-12-01"`
- [x] an exception

#### What is the correct output for:

```ruby
d = Date.parse('2019-01-31') >> 1
p d.to_s
```

- [ ] `"2018-12-31"`
- [ ] `"2020-01-31"`
- [ ] `"2019-02-31"`
- [x] `"2019-02-28"`
- [ ] an exception


#### What is the correct ways to access the value of this Hash?

```ruby
toybox = { "doll" => 'Sally' }
```

- [ ] `toybox.doll`
- [x] `toybox['doll']`
- [x] `toybox["doll"]`
- [ ] `toybox[:doll]`
- [x] `toybox.try('doll')`

#### The following regexp is incorrect please fix it, it should *ONLY* match:

- .ts
- .ts.erb
- .tsx
- .tsx.erb

`/^\.(ts|tsx)(\.erb)?$/`

Here is a good editor for regexp, maybe try and do it without using it first tho: https://rubular.com/

#### Given the following file locations, what are the outputs?

```ruby
# /User/gollum/precious/ring.rb
File.dirname(__FILE__)
```

- precious

```ruby
# /User/tom/junk/ring.rb
File.path(__dir__)
```

- /User/tom/junk/

#### Write the following method that would give me the correct return value:

```ruby
bark { "Oki" }
=> "Oki yips!"
```

- *give me answer*
```ruby
def bark doggo
   puts "#{doggo} yips!" 
end
```

#### What is the result of the following:

```ruby
teams = [['greg', 'bob']]
teams << if teams.size < 2
  ['jim', 'jerry']
elseif teams > 2  #is this a trick question because pretty sure ruby doesn't spell elsif properly
  ['sam']
else
  ['tony']
end

p teams.flat_map { |t| t }
```
['greg','bob','jim','jerry']
