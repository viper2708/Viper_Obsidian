## Course Overview

* Topics covered :
    * Using Servlets to build web applications
    * Using Java ServerPages to return HTML content
    * Using Servlets and Java ServerPages together
    * Using filters to compress data
    * Using event handlers

* Prerequisites
    * Programming in Java

## Introduction

* Java Web Programming
    * Java web typically made up of Servlets and Java Server Pages
        * Many frameworks, e.g. Struts build on top of these specifications
        * There are other aspects such as Filters and Listeners

* Deploying to a weeb server
    * Unit od deployment is called a 'web application'
        * A web application is a deployable unit of content and configuration
        * Request routed to application using URL base
        * Web applications may contain static content
        * Web applications may contain dynamically generated content

* Deployment
    * Java web applications have a standard structure
        * Applications can be deployed by simply copying files
    * Can also deploy as a .war file
        * Web Archive

## Writing Servlets

* Servlet interface
    * Method index
        * destroy()
            * Cleans up whatever resources are being held (e.g., memory, file handles, threads) and makes sure that any persistent state is synchronized with the servlet's current in-memory state.
        * getServletConfig()
            * Returns a servlet config object, which contains any initialization parameters and startup configuration for this servlet.
        * getServletInfo()
            * Returns a string containing information about the servlet, such as its author, version, and copyright.
        * init(ServletConfig)
            * Initializes the servlet.
        * service(ServletRequest, ServletResponse)
            * Carries out a single request from the client.

* Request Routing
    * Server routes request to servlet using configuration info
        * Held in web.xml
        * By default, one servlet instance handles all requests to associated URL

* Servlet mapping in web.xml
```
        <web-app>
            <servlet>
                <servlet-name>Home</servlet-name>
                <servlet-class>com.pronit.OurServlet</servlet-class>
            </servlet>
            <servlet-mapping>
                <servlet-name>Home</servlet-name>
                <url-pattern>/Bar</url-pattern>
            </servlet-mapping>
            <servlet-mapping>
                <servlet-name>Home</servlet-name>
                <url-pattern>*.abc</url-pattern>
            </servlet-mapping>
        </web-app>
```

* HTTP Request Processing
    * HttpServletRequest wraps an HTTP request
    * HttpServletResponse wraps the potential HTTP response

* Using Initialization Parameters
```
        <web-app>
            <servlet>
                <servlet-name>Foo</servlet-name>
                <servlet-class>con.pronit.OutServlet</servlet-class>
            </servlet>
            <init-param>
                <param-name>connstr</param-name>
                <param-value>server=home;catalog=pubs;uid=sa;pwd=;</param-value>
            </init-param>
        </web-app>

        import javax.servlet.*;
        import javax.servlet.http.*;
        import java.IO.*;
        @WebServlet(urlPatterns = {"/home", "*.do"}
                    initParams =
                    {
                        @WebInitParam(name = "connstr",
                                    value="server=...")
                    })
        public class OurServlet extend HttpServlet {
            public init() {
                connstr = getInitParameter("connstr");
            }
            ...
        }
```
* ServletContext
```
        <web-app>
            <context-param>
                <param-name>connstr</param-name>
                <param-value>server=home;catalog=pubs;uid=sa;pwd=;</param-value>
            </context-param>
        </web-app>

        public class OurServlet extends HttpServlet {
            String connstr;
            public void init() {
                connstr = getServletContext().getInitParameter("connstr");
            }
        }
```

## JavaServer Pages

* Summary
    * JSPs are a mixture of
        * Text
        * Script
        * Directives
    * JSP is the View in an MVC style web application
        * Hide the pages in WEB-INF

## The Expression Language

* Why an Expression Language?
    * Previous versions on JSP relied on Java as the scripting language
        * Made it difficult to produce dynamic pages
        * JSP 2.0 introduced an EL
        * EL is very 'page-author' friendly
        * Allows page authors a limited form of page scripting

* Using the Expression Language
    * Syntax
        * Always use ${expr} contruct
    * EL can be used on page
        * This will simply output the value of the expression
```
        <span>Name: ${user.name}</span>
```

* Accessing JavaBeans
    * Can get bean property's
        * use either .(dot) or [] syntax
            * user.name
            * user["name"]
        * can use [] for access to lists, maps, arrays and beans
        * can nest arbitrarily
            * a["name"].first
            * a["name"]["first"]
        
* Implicit Objects
    * EL has access to a set of implicit objects
        * All Maps (except pageContext)
            * requestScope
            * applicationScope
            * paramValues
            * headerValues
            * initParam
            * pageScope
            * sessionScope
            * param
            * header
            * cookie

* Expression Language Operators
    * Expressions can use operators
        * Mathematical
            * + - * / div % mod == eq != ne
            * < lt > gt <= le >= ge
        * Logical
            * && and ! not || or
        * Empty operator
            * Empty

* Summary
    * The Expression Language
        * Not a "full" language
        * Gives access to properties on JavaBeans
        * Can use the '.' or '[]' syntax
        * Has access to built in intrinsics
        * Has a set of operators
        * Can access collections

## The Java Standard Tag Library

* Why Tags?
    * Provide encapsulation of (UI) logic
    * Replace script on a page
    * Better for page designers than having to write Java code

* What is a 'TagLibrary'?
    * Tag libraries are collections of tags
    * The Java Standard Tag Library (JSTL) is a set of standard tags used in JavaServer Pages

* Using Tags
    * Tags are managed as libraries
        * Individual tags are Java classes
        * Tag metadata held in Tag Library Desciptor file
        * Collected together in a JAR file

* Core tags
    * Conditional
        * If
        * Choose - when or otherwise
    * Iteration
        * Two tags, for-each and for-tokens that support
            * Exporting an object that holds the current value
            * Ranges to iterator
            * Exposure of a status variable
    * Import
        * Managing text is an important part of JSP
            * <c:import> == <jsp:include>++
        * Can import from
            * This context
            * Another context on this server
            * Another server
        * Imported data can be
            * Written to page
            * Stored in a string
            * 'stored' in a Reader
    * URL
        * There are issues with relative URLs in a web application
        * No concept of a 'web application'
        * Using '/[url' give server relative URLs
            * /somepage.jsp
            * http://myserver.com/somepage.jsp
        * Using '[url]' somewhere.jsp
            * is relative to the page
            * From foo/index.jsp would give
            * http://myserver.com/myapp/foo/somepage.jsp
        * <c:url ... />
            * Allows the creation of application relative URLs
            * Also adds session encoding where necessary
        * Can specify
            * 'value' of URL
            * 'params' to be added
            * Can create application relative URLs
            * Application relative URLs start with a '/'
        * Set 'context' param if importing from a foreign context

* Summary
    * JSTL provides a core set of tags
    * These allow page authors control over 'view' logic
    * Allow better control over URLs
    * Other functionality also provided
        * SQL
        * XML

## Writing Tag Libraries

* Tags are a great way of extending JSP functionality
* Tags can be written in Java
* Tags can be written in JSP
* Tags can be passed 'simple' data as attributes
* Tags can be passed as fragments of HTML as attributes
* Tags can be variables

## Event listeners

* Annotations - Reminder
    * Can replace or augment settings
        * web.xml
    * Only these are scanned
        * classes in WEB-INF/classes
        * JARs in WEB-INF/lib
    * Can set metadata-complete="true" on web-app
        * Stops any scanning for annotations

* What Annotations exist?
    * @WebServlet
    * @WebFilter
    * @WebInitParam
    * @WebListener
    * @MultipartConfig

* Event Listeners
    * Events are fired at users at appropriate times
        * Application Events at app start/end
        * Session Events at Session start/end
        * Request Events at Request start/end
        * Attribute events when attribute added/removed
        * Listeners listen for events

* Listener Implementation
    * Listeners Implement Appropriate Interface
        * ServletContextListener
        * ServletContextAttributeListener
        * HttpSessionActivationListener
        * HttpSessionAttributeListener
        * ServletRequestListener
        * ServletRequestAttributeListener
        * Passed appropriate "Event" object

* Registering Listeners
    * Listeners are registered in web.xml
        * Fire in order of listing for activation
        * Fire in reverse order for deactivation
```
        <listener>
            <listener-class>
                com.mantisso.WhitePagesListener
            </listener-class>
        </listener>
```

* Listeners Annotations
    * @WebListener

* Application Listener
    * Implements ServletContextListener
    * Fired at application Start/End
    * Passed a ServletContextEvent
        * Gives access to ServletContext

* Session Listener
    * Fired after Session start
    * Fired before Session ends
        * In servlet 2.3 spec fired after session ended
    * Passed and HttpSessionEvent gives access to
        * HttpSession

* Request Listener
    * Fired before request comes into scope
        * Before it enters first filter in the chain
    * Fired before request goes out of scope
        * After it's left the last filter
    * ServletRequestEvent gives access to
        * ServletContext
        * ServletRequest

* Listener issues - Exceptions
    * Application initiated Exceptions
        * e.g. adding an object to a session causes listener to throw exception
        * Exception passed to application
        * No more listeners fired
    * Container initiated exceptions
        * e.g. Application listener causes exception at start-up
        * Not handled by application
        * May cause container to make application unavilable
        * Container will return HTTP 500 status code

* Summary
    * Web applications fire 'events'
    * EventListeners can respond to these
    * Manage application/ session/ request start/ end
    * Configure in web.xml or annotations

## Writing filters

* What is a filter?
    * Code that intercepts a request and does extra processing
        * They are executed before / after the request is executed
        * The request could be to a servlet / JSP / HTML etc.
        * Request / Response could be modified in the filter
        * Filters can be executed as a part of a chain
        * Filters can intercept original request
        * Filters can intercept forwards and includes
        * Can use filters to provide :
            * Session management
            * Logging
            * Security
            * XML transforms
        * The filters are called synchronously, so this trace all happens on the same thread
        
* Writing filters
    * Filter writers implement javax.servlet.Filter
        * doFilter() may "wrap" Request and/or Response
        * Call chain.doFilter(...) to pass on the request
        * doFilter can dispatch the request to a different resource
        * doFilter may return to the caller without chaining the request

* Filter configuration
    * Filter Configures in Deployment Descriptor
        * Maybe associated with a URL
        * Maybe associated with a named resource

* Initialisation Method
    * Called once when the filter is loaded
        * Passed a reference to a FilterConfig
        * Use this to get a reference to the ServletContext if necessary
        * diFilter is passed the request, response and the filter chain

* Wrapping Request
    * Can extend HttpServletRequestWrapper
        * Adaptor class that takes original request object as constructor parameter
        * Default behaviour is to simply call the original request
        * Override necessary methods
        * Can : invent headers, change attributes, log calls, etc.

* Wrapping Response
    * Filter may want to change response
        * Can create
            * HttpServletResponseWrapper
        * More interesting than
            * HttpServletRequestWrapper
        * Have to cope with (at least) content length, content type, getWriter and getOutputStream

* Filters under Forward and Include
    * Default behaviour for filters is to not work under forward/include
    * Servlet 2.4 specificatios intorduces this ability

* Annotations
    * @WebFilter
        * name
        * urlPatterns (required)
        * dispatcherType
        * servletName
        * asyncSupported
        * ...and others
    * @WebInitParam
        * Used to parameterize the filter

* Summary
    * Filters allow us to add services to Web applications
    * Extremely powerful addition to the servlet specification
    * Request Wrappers allow us to change the request data that a resource sees
    * Response Wrappers allow us to filter responses before they are sent to the client

## Asynchronous Programming

* Why Asynchronous Servlets?
    * Slow backend resources
    * Reuse of threads
    * Server Push

* How do Asynchronous Servlets work?
    * Get and asynchronous context
    * Start the context to handle the request
    * Use the context to return the responses
    * (Optionally) Add a 'listener' to handle events

* Async filters
    * Filters can also be asynchronous
    * Mechanism similar to Servlet

* Summary
    * Servlet 3 specification introduced asynchronous behaviour
        * Servlets
        * Filters
    * Be careful while using
        * May end up offloading one thread to another with no benefit