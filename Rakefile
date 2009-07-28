# PyLint messages to disable
pylint_disable = ["R0903", "C0103", "R0903", "F0401"]
task :default => [:pep8, :pylint, :test]

def title(text)
  padding = "#" * (79 - (text.length + 1))
  puts "#{padding} #{text}"
end

task :clean do
  `rm *.pyc`
end

task :pep8 do
  title("pep8.py")
  puts `python tools/pep8.py --repeat *.py tests/*.py`
end

task :pylint do
  title("PyLint")
  puts `pylint --reports=n --disable-msg=#{pylint_disable.join(",")} *.py tests/*.py`
end

task :test do
  title("Unit tests")
  puts `nosetests`
end