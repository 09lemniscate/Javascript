#Questions related to Javascript

Core Javascript

1. Difference between null and undefined.

2. Implement clearAllTimeOuts

3. What is client side rendering and how is it different from server side rendering?
	Client-side rendering allows developers to make their websites entirely rendered in the browser with JavaScript. Instead of having a different HTML page 		per route, a client-side rendered website creates each route dynamically directly in the browser. This approach spread once JS frameworks made it easy      to take.
	Server-side rendering allows developers to pre-populate a web page with custom user data directly on the server. It is generally faster to make all the     requests within a server than making extra browser-to-server round-trips for them. This is what developers used to do before client-side rendering.
  What is the difference between client-side and server-side rendering?
  Client-side rendering manages the routing dynamically without refreshing the page every time a user requests a different route. But server-side rendering   is able to display a fully populated page on the first load for any route of the website, whereas client-side rendering displays a blank page first.

	Server-side pros:
	Search engines can crawl the site for better SEO.
	The initial page load is faster.
	Great for static sites.

	Server-side cons:
	Frequent server requests.
	An overall slow page rendering.
	Full page reloads.
	Non-rich site interactions.

	Client-side pros:
	Rich site interactions
	Fast website rendering after the initial load.
	Great for web applications.
	Robust selection of JavaScript libraries.

	Client-side cons:
	Low SEO if not implemented correctly.
	Initial load might require more time.
	In most cases, requires an external library.
	
4. Machine Coding : Design the facebook comment wizard( nested comments)
	
	https://codesandbox.io/s/gracious-germain-xzgryq?file=/index.html
	
5. Machine Coding : Snackbar
		
		https://www.w3schools.com/howto/howto_js_snackbar.asp
		
6. Machine Coding : Design Calender
7. Difference between http & https
8. Event Loop - micro and macro tasks
9. How JS is executed
10. How webpage is rendered . Steps taken by browsers
11. CORS
12. Security Issues : XSS, Cross-Site Request Forgery , Cookies in depth
13. Basics of Javascript - Number(5) , new Number(5) , 6
14. Polyfills - Promise.all, flattenArray, Bind, HOF- reduce,filter,map
15. Accessibility in HTML
16. Currying
17. Closures - lexical scoping
18. JS Engine
19. Garbage Collector
20. Memoization in JS
21. Debounce throttle




7. Web Performance

	1. Critical Rendering Path
	2. Web Vitals - LCP, FID, CLS
	3. Rendering blocking scripts
		CSS blocks rendering, so you need to deal with it right away (i.e. at the top of the document, in your <head>).
		JS blocks downloads, so you need to deal with these last to ensure that they don’t hold up anything else on the page.
		CSS blocks rendering because of a browsers desire to render pages progressively; they want to render things as they get to them, and in order.
		If styles are a long way down the page the browser can’t render that CSS until it gets to it. This is so that the browser can avoid redraws of styles if they alter something that was previously rendered further up the document. A browser won’t render a page until it has all the available style information, and if you put that style information at the bottom of the document you’re making the browser wait, blocking rendering.
		So, you put your CSS at the top of the page so that the browser can start rendering right away.
		JavaScript blocks downloads for a number of reasons (this is the browser being clever again) but firstly, we need to know how downloading assets in browsers actually happens; simply put, a browser will download as many assets as it can from a single domain in parallel. The more domains it is pulling from, the more assets can be downloaded, in parallel, at once.
		JavaScript interrupts this process, blocking parallel downloads from any and all domains, because:
		The script being called might alter the page, meaning the browser will have to deal with that before it can move on to anything else. In order for it to deal with that eventuality it stops downloading anything else in order to focus solely on that.
		Scripts usually need to be loaded in a certain order for them to work, for example, loading jQuery before you load a plugin. Browsers block parallel downloads with JavaScript so that it doesn’t start downloading jQuery and your plugin at the same time; it should be pretty obvious that if you were to start downloading both in parallel, your plugin would arrive before jQuery would.
		So, because browsers stop all other downloads whilst JavaScript is being fetched, it is usually a good idea to put your JavaScript as late in the document as possible. I’m sure you’ve all seen blank sections of pages where a third party piece of JS is taking ages to load and blocking the fetching and rendering of the rest of the page’s assets; this is JavaScript’s blocking in action.
	4. Image Optimisation-
		1 :Choose the correct image format
		PNG: Higher quality and high size images, big size, lossless compression (can be lossy as well), can be used for transparent bg.
		JPEG: Good quality and can use lossless (can be lossy as well). Use it for images with many colors. Small file size.
		GIF: use only 256 colours and uses lossless compression . Best for animated images.

		There are other formats as well which are good but some or the other browsers dont support them or are not universally acceptable.
		Good comparison for types: https://searchengineland.com/images-easiest-page-speed-win-269742

		Lossy compression:- Filter which eliminates some of the data and may reduce the quality of image. You have to be careful how much compression you do so it does not degrade the quality of images you serve on website.File size is greatly reduced.

		Lossless compression:- Removes the metadata of images and compress the image(which can be restored later). Doesn't degrade the quality of images but also size is also not reduced that much.

		Source : https://kinsta.com/blog/lossy-compression/
		https://kinsta.com/blog/optimize-images-for-web/

		2:Optimise Dimensions:
		Optimising dimensions can be of great help. Lets say an image of 800px * 600px is being displayed in desktop site and the same image is being shown in msite as well. Whats the issue here?
		The mobile device is small and doesnt need this much big file to display. The image dimension can be optimised and served as per the need by which device it is being opened upon. High dimension site can show larger dimension image and same for small dimension devices.

		3:Using CDN:
		A content delivery network, or CDN, is a geographically diverse network of servers that helps speed up page load time by reducing the distance between the website visitor and the server.

		4:Optimize meta data:
		Rename your images to what they are: Good for SEO
		Include Alt tag and use responsive images: Good for SEO
		Source :https://www.websitebuilderexpert.com/grow-online/image-optimization-guide/

		5:Lazy loading and blur loading
		Implement lazy loading within your code for faster loading of images.
