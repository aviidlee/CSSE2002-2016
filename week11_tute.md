# Week 11 Tutorial

## DO EVALUATIONS 

## Objectives 
- Get you guys started on the assignment! 

## Some notes on the spec & getting started
- Make a checklist of the things it needs to do
- GUI readability and intuitiveness 
	- Does not need to be fancy; main thing is not to confuse tutors
	- Label your buttons and textboxes appropriately 
	- It should be easy to work out what to do 
	- Your GUI should scale in the sense that I should be able to see the 
	  information even when there's a lot of it; e.g., if there is a long route,
	  there shbould be, for instance, a scrollbar so I can see the whole thing
- You need to have public methods in this assignment since components of mvc
  need to talk to each other, but this does NOT mean you should just make 
  everything public; do not expose implementation details unnecessarily.
- Note that you need class invariants (and you need to protect these)! 

- Recommended sequence
	- Draw out the view 
	- Code the view 
	- Write model and controller 

## Java GUI Basics 
- Has everyone done the GUI Prac (prac 5)? If not, DO IT! 

## Model-View-Controller Pattern
- Model: knowledge; application logic. Knows nothing about UI. 
- View: ask the model for data, tell model to update itself.
- Controller: respond to events and control what the view shows by talking to 
  view and model 
