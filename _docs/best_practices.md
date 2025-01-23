# Best Practices

Collection of practices to increase efficiency and maintainability of your
project and codebase. These guidelines are generally agreed upon to be the most 
flexible and 'correct' solutions. They are, however, not the only solution
and you may choose to follow different guidelines for one reason or another.
What's important is that your code and organization remain *consistent*.


## File Structure

> Godot's documentation for
> [project organization](https://docs.godotengine.org/en/stable/tutorials/best_practices/project_organization.html)

 The file tree has three root folders:

- ***autoloads***
    - This folder is used to store all autoloaded files. These are files
      which are always loaded and globally accessible. They are useful for
      commonly referenced code and important data which needs to be easily
      accessed across all classes.
- ***common***
    - This folder houses all assets which are used by multiple sources or
      which are used for the application itself (i.e. the boot splash or
      icon).
- ***scenes***
    - This folder contains all scenes that are used in the project. Everything
      from the player to the main menu is in this folder. Subfolders within
      help to organize these scenes -- by use or any manner which you'd like.
  
> An optional fourth folder ***addons*** can be created if your project
> uses third-party assets or plugins. The purpose of this folder is to
> help seperate external code and assets from your own work.

**Notes**:

- Within the ***scenes*** folder and within its subfolders, scenes should be
  packaged with all assets necessary to their function. This typically includes
  a .tscn file, a .gd file, one or more sprites, and in some cases audio or other
  file types. By keeping all relevant assets together, it is easier to work with
  the scene and to move it within the project or to other projects entirely.
- Autoloads cannot have a `class_name` that matches their autoload name. This is
  typically only an issue if you wish to have documentation for the class as
  the fact that it is autoloaded would otherwise make the `class_name` redundant.
  To circumvent the issue I prefix these scripts' `class_name` with 'Docs'. (e.g. `DocsSceneManager`)

File structure is largely personal preference, this particular method of organization
is something that I have found to be useful. This does not, however, make it 'correct'
nor the only option. 


## Style Guide

> Godot's documentation for
> [GDScript](https://docs.godotengine.org/en/stable/tutorials/scripting/gdscript/gdscript_styleguide.html)
> and for [C#](https://docs.godotengine.org/en/stable/tutorials/scripting/c_sharp/c_sharp_style_guide.html)
