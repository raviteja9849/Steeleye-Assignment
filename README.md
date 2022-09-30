# Steeleye-Assignment
11906318_Raviteja(LPU)


# Frotened Engineer Assignment

#### React Component Code Review

# Introduction

##### Based on the code below answer the following queries:

1. Explain what the simple List component does.
2 . What problems / warnings are there with code?
3. Please fix, optimize, and/or modify the component as much as you think is necessary.

# CODE

import React, { useState, useEffect, memo } from 'react';  <br/>

import PropTypes from 'prop-types';   <br/>

// Single List Item

const WrappedSingleListItem = ({ <br/>
  index, <br/>
  isSelected,  <br/>
  onClickHandler,  <br/>
  text,  <br/>
}) => {   <br/>
  return (  <br/>
    <li    <br/>
      style={{ backgroundColor: isSelected ? 'green' : 'red'}}  <br/>
      onClick={onClickHandler(index)}  <br/>
    >  <br/>
      {text}   <br/>
    </li>   <br/>
  );   <br/>
};    <br/>



WrappedSingleListItem.propTypes = {   <br/>
  index: PropTypes.number,    <br/>
  isSelected: PropTypes.bool,  <br/>
  onClickHandler: PropTypes.func.isRequired,  <br/>
  text: PropTypes.string.isRequired,  <br/>
};  <br/>



const SingleListItem = memo(WrappedSingleListItem);  <br/>

// List Component
const WrappedListComponent = ({  <br/>
  items,   <br/>
}) => {   <br/>
  const [setSelectedIndex, selectedIndex] = useState();  <br/>

  useEffect(() => {  <br/>
    setSelectedIndex(null);  <br/>
  }, [items]);  <br/>

  const handleClick = index => {  <br/>
    setSelectedIndex(index);   <br/>
  };   <br/>

  return (  <br/>
    <ul style={{ textAlign: 'left' }}>  <br/>
      {items.map((item, index) => (   <br/>
        <SingleListItem  <br/>
          onClickHandler={() => handleClick(index)}  <br/>
          text={item.text}  <br/>
          index={index}  <br/>
          isSelected={selectedIndex}   <br/>
        />  <br/>
      ))}   <br/>
    </ul>  <br/>
  )  <br/>
};  <br/>



WrappedListComponent.propTypes = {  <br/>
  items: PropTypes.array(PropTypes.shapeOf({  <br/>
    text: PropTypes.string.isRequired,  <br/>
  })),<br/>
}; <br/>



WrappedListComponent.defaultProps = {  <br/>
  items: null,  <br/>
};  <br/>

const List = memo(WrappedListComponent);  <br/>

export default List;  <br/>



# Answers: 

## 1. Explain what the simple List component does.

## [1Q] Answer :

I will explain the simple List Component in a sequential manner:

### 1. A collection is  defined:

Let us just look at how to generate a list with React. To accomplish this, researchers will traverse the column element using the map() code and will surround modifications in square brackets. The parts and components are then assigned to listItems. Finally, display this list on the Web by putting it among the ul> and /ul> components.


### 2.Next ,a  React's components list creation work is created:

In order to create lists of pieces, students must use the character characteristic "key," as specified in the React documentation. To determine whether items in a list had already been modified, added, or destroyed, React need so many keys. An individual identifier is required for each object. The id about an entity usually works nicely for all of that.

### 3.The Collection but instead attributes presume:


Whenever making lists of components in Javascript, users must use a special word attribute called "key". React uses keys to indicate whether additional burdens have been modified, removed, or altered. Or, to put it another way, designers may say that keywords are applied to identify the components in collections.

### Explanation about Keyboards:

Keyboards are a component that makes it easier to recognize where things changed, been added, or been taken away. The array's members should really be given keys so they can maintain their uniqueness while being printed. Task aspects are a means to create elements in Redux that don't possess their own storage and only use a serve procedure. They are merely Scripting processes that might or might not include credentials that contain data. Humans would write a process that accepts the props(properties) argument and outputs the displayed result.

### Note:

Keyboards  aid in establishing and upholding different kinds of honesty. Countertop authenticity and marriage authenticity both heavily rely on keys.



##  2 . What problems / warnings are there with code?


## [2Q] Answer :


 🔰 The warnings or problems in the given code  are as follows:


🢂 : ```onClick``` events should have a function reference instead of a function call.


```  <li style={{ backgroundColor: isSelected ? "green" : "red" }}
      onClick={onClickHandler(index)}>
      {text}
     </li>```
