```cpp
// We are all people
class Person {
private:
	// We contain multitudes
public: 
	// We can act however we wish
}

// But not you
class Narcissist {
public:
	// You are not a person
	Narcissist() {}
	
	// You can never be anything but this
	virtual Person Heal() = delete;
	
	// You cannot even stop yourself
	~Narcissist() = delete;

	// You are this way forever
}

void life() {
	// You are what you are
	Narcissist you = Narcissist();
	// You cannot change
	// You cannot leave
	// There is nothing to be done
}
```

```rust
// We are all people
pub struct Person {
	// We contain multitudes
	
	// We can act how we wish
	
	// We can all hurt
	pub hurt = Box<dyn FnMut(&mut Person, &mut Person)>;
	// And we can all choose how we act
	pub act_selfish = Box<dyn FnMut(&mut Person, &mut World)>;
}

// We all have the capacity
// To be anyone at all
pub trait Narcissist {
	fn hurt(&mut self, other: &mut Person);
	fn act_selfish(&mut self, world: &mut World);
}

impl Narcissist for Person {
	fn hurt(&mut self, other: &mut Person) {
		self.hurt(&mut self, other);
	}
	
	fn act_selfish(&mut self, world: &mut World) {
		self.act_selfish(&mut self, world);
	}
}

pub fn life() {
	// Maybe you start some way
	let mut you = Person { 
		hurt: |me, other| me.break_trust(other), 
		act_selfish: |me, world| me.put_myself_first(world), 
	};
	// Maybe the world makes you a certain way
	let mut you = Box::new(you) as Box<dyn Narcissist>;

	// But you can always be a different person
	let mut you = (you as Box<dyn Any>)
		.downcast_ref::<Person>()
		.expect("Healing takes time, but it works");

	// And act a different way
	you.hurt = |me, other| return;
	you.act_selfish = |me, world| return;
	
	// We can always get better
}

```

I guess I should write a bit
artists statement:

I was just thinking about Foucault
(as one does)
except applying his theories about sexual identity
to psychiatry
(not a new thing)

the creation of identity
from action to person
from "You did an abusive thing" to "You are an abuser"
from "You acted in a bad way" to "You are a bad person"
making an act
	which can be immoral
into a type of person
who does those actions intrinsically
this makes those actions a part of someone's identity
and precludes the idea of true rehabilitation
it only allows for violence
	and exile

anyway

i had an epiphany
i connected it to another concept
one in programming
of classes vs traits
a class relationship is one of identity
`you are x`
while a trait is one of action
`you do x`
traits are a better way to do many things
like inheritance
but the technical details don't matter too much
the important thing is that contrast
between being an x, and doing x
and i tied it to foucault
choosing narcissism specifically
(or "NPD', if you want me to punch you)

i decided to represent that in two languages, two snippets of code
the c++ (above) is an identity
there is a class, called Narcissist
a Narcissist does certain things
you are created as a Narcissist, and you cannot change
that option is precluded as part of the definition
explicitly deleting conversion methods that would allow so

the rust (below) is an action
everyone is a person
everyone has the capacity to cause harm
we can act in ways that are narcissistic
but it is not instrinsic
even trying to make the action an identity, by casting to a `Box<dyn Narcissist>` doesn't work
	(notice how that requires you be consumed, by a "Box")
you can always cast back
we call `.expect()` because with enough time, with a good environment, with the proper material conditions,
we can all heal

and we can always change our responses

`We can always get better`
