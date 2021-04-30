Dans le fichier html fourni, faire grandir le texte au scroll.

The onmousedown event occurs when a user presses a mouse button over an element.
    Tip:  The order of events related to the onmousedown event (for the left/middle mouse button):
               onmousedown
               onmouseup
               onclick <<<
          The order of events related to the onmousedown event (for the right mouse button):
               onmousedown
               onmouseup
               oncontextmenu <<<

HTML exemple:
-------------
  <p id="textId" onmousedown="mouseDownDetected('textId',event.which)" 
                 onmouseup="mouseUpDetected('textId',event.which)" 
                 onmouseenter="mouseEnterDetected('textId',event.which)"
                 onmouseleave="mouseLeaveDetected('textId',event.which)"
                 onmouseout="mouseOutDetected('textId',event.which)"
                 onmouseover="defaultSizeText('textId',event.which)"
                 >

JS corresponding:
-----------------
   function mouseDownDetected(tagId, buttonNb)
   {
      console.log(`mouseDownDetected ${tagId} - ${buttonNb}`);
      defaultSizeText( tagId, buttonNb);
   }

   function defaultSizeText( tagId, buttonNb)
    {
      console.log(`defaultSizeText ${tagId}, button ${buttonNb}`);
      let xxId= document.getElementById(tagId)
      if (xxId == null)
      {
        alert(`No tag : ${tagId}`);
      }
      else
      {
        xxId.style.fontSize= "16px";
      }
    }

OR scan periodicaly the windows scrooling mouvement !
see https://www.w3schools.com/jsref/met_win_setinterval.asp
https://www.javatpoint.com/javascript-setinterval-method
https://www.bitdegree.org/learn/javascript-setinterval

