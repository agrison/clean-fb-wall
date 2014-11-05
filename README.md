Clean your Facebook Wall
=============

## Process

Add a bookmark to your Chrome with the following content:

    javascript:!function(){function e(){holder=document.createElement("div"),holder.id="fbwd",firstStory=document.querySelector("div.lastCapsule").nextSibling,holder.className=firstStory.className+" "+firstStory.querySelector("div").className,newPost=document.querySelector("div.timelineUnitContainer").querySelector('button[type="submit"]'),innerHTML='<div style="text-align:center"><h2 style="color:#3b5998;text-align:center;font-size:2em;margin-bottom:5px;">Facebook wall delete</h2><br/>',innerHTML+='<p style="font-size:1.25em">',innerHTML+='<span style="color: #6a7480; font-weight:bold">Current status:</span> ',innerHTML+='<span style="color: #3b5998" id="currentStatus">Waiting...</span>',innerHTML+="</p>",innerHTML+='<p style="font-size:1.25em">',innerHTML+='<span style="color: #6a7480; font-weight:bold">Popups activated:</span> ',innerHTML+='<span style="color: #3b5998" id="activatedPopups">0</span>',innerHTML+="</p>",innerHTML+='<p style="font-size:1.25em">',innerHTML+='<span style="color: #6a7480; font-weight:bold">Stories to delete:</span> ',innerHTML+='<span style="color: #3b5998" id="storiesToDelete">0</span>',innerHTML+="</p>",innerHTML+="<p>",innerHTML+='<button id="continueDeletion" class="'+newPost.className+'">CLEAN MY WALL !</button>',innerHTML+="</p>",innerHTML+="</div>",holder.innerHTML=innerHTML,document.querySelector("div.lastCapsule").appendChild(holder)}window.fbwd={},window.fbwd.scroll=0,window.fbwd.scrollAttempts=0,window.fbwd.eventFire=function(e,o){if(e.fireEvent)e.fireEvent("on"+o);else{var t=document.createEvent("Events");t.initEvent(o,!0,!1),e.dispatchEvent(t)}},window.fbwd.click=function(e){window.fbwd.eventFire(e,"click")},window.fbwd.clickAll=function(e,o){for(i=0;i<e.length;++i)window.fbwd.click(e[i]),o&&o()},window.fbwd.log=function(e){document.getElementById("currentStatus").innerHTML=e+"..."},window.fbwd.scrollToBottom=function(){window.fbwd.scroll<document.body.scrollHeight?(console.log("scrolling"),window.fbwd.scroll=document.body.scrollHeight,window.fbwd.scrollAttempts=0,window.scrollTo(0,document.body.scrollHeight)):(console.log("not scrolling"),window.fbwd.scrollAttempts++)},window.fbwd.infiniteScrollToBottom=function(){window.fbwd.scrollAttempts<5?(window.fbwd.scrollToBottom(),setTimeout(window.fbwd.infiniteScrollToBottom,500)):(e(),aPopUp=document.querySelectorAll('div.fbTimelineCapsule a[aria-haspopup="true"][aria-label="Story options"]'),window.fbwd.toDelete=aPopUp.length,window.fbwd.log("Will activate "+aPopUp.length+" story options popups"),window.fbwd.clickAll(aPopUp),window.fbwd.log("Done"),document.getElementById("activatedPopups").innerHTML=aPopUp.length,window.fbwd.log("Discarding popups"),window.fbwd.click(document.getElementsByTagName("body")[0]),window.fbwd.log("Finding all visible delete handlers"),window.fbwd.locateDeleteHandlers=function(){aDelete=document.querySelectorAll('a[data-feed-option-name="FeedDeleteOption"]'),aDelete.length===window.fbwd.toDelete?(window.fbwd.toDelete=aDelete,document.getElementById("storiesToDelete").innerHTML=aDelete.length,window.fbwd.log("Waiting on you to accept or cancel")):(window.fbwd.log("Searching for stories to delete"),setTimeout(window.fbwd.locateDeleteHandlers,1e3))},window.fbwd.locateDeleteHandlers(),document.getElementById("continueDeletion").onclick=window.fbwd.continueDeletion)},window.fbwd.continueDeletion=function(){window.fbwd.log("Deleting..."),window.fbwd.delStatus={index:0,clickedDelete:!1,clickedConfirm:!1},window.fbwd.doDelete=function(){if(window.fbwd.delStatus.clickedDelete)if(btn=document.querySelectorAll('div[role="dialog"] button'),window.fbwd.delStatus.clickedConfirm){if(dialog=document.querySelectorAll('div[role="dialog"]'),dialog.length>0)for(i=0;i<dialog.length;i++)dialog[i].parentNode.removeChild(dialog[i]);window.fbwd.delStatus.index<window.fbwd.toDelete.length-1?(window.fbwd.delStatus={index:window.fbwd.delStatus.index+1,clickedDelete:!1,clickedConfirm:!1},setTimeout(window.fbwd.doDelete,100)):(window.fbwd.log("All done. Will refresh in two seconds"),setTimeout(function(){location.reload()},2e3))}else btn.length>0&&(window.fbwd.click(btn[0]),window.fbwd.delStatus.clickedConfirm=!0),setTimeout(window.fbwd.doDelete,100);else window.fbwd.click(window.fbwd.toDelete[window.fbwd.delStatus.index]),window.fbwd.delStatus.clickedDelete=!0,setTimeout(window.fbwd.doDelete,100)},window.fbwd.doDelete()},window.fbwd.infiniteScrollToBottom()}();
    
Then go to your timeline, and click your bookmark file.

The process will scroll on your timeline until it cannot find something new, then will get to the top of the page showing you a little box with a button that you need to click to clean your entire wall.

Click it and wait until it has finished. At the end of the process the page will refresh, you should see no more posts on your timeline.
    
## The code

This is the code documented:
