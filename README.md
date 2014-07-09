AndroidQuiz
===========

A simple quiz app for universal Android knowledge.

#Universal Android Knowledge Quiz

##1. Your First App - Framework Basics

In the app creation wizard, what is the package name you specify used for?

What are resources used for?

What does R.java do? What are the numbers it contains for?

When is R.java built?

Why are ids specified with @+id/foo rather than @id/foo?

What can I call from an anonymous inner class?

When I run GeoQuiz, how does my code in QuizActivity get run?

What is your personal recommendation for a default emulator setup?

##2. Android MVC

Name the major model, view, and controller components in the Android standard libraries.

##3. Android Lifecycle

Give real world examples of activities in the running state, paused state, and stopped state.

What happens to an activity when the screen rotates? Why?

If your activity is currently in the running state, which lifecycle callbacks are guaranteed to be called before it is destroyed?

Where does the savedInstanceState bundle live?

When is it *not* appropriate to store your data in savedInstanceState?

##4. Debugging Android Apps

What is the first thing I should do if DDMS can't find my emulator or device?

##5. Your Second Activity

What is an Intent?

What makes an intent "explicit"?

How does Serializable work? When is it inappropriate to mark an object Serializable?

What kind of data should *not* be passed in an Intent?

What result is returned to the calling activity if I run the following activity instance method:

    public void returnResult() {
        setResult(Activity.RESULT_CANCELED);

        finish();

        setResult(Activity.RESULT_OK);
    }

##6. Android SDK Versions And Compatibility

Where are minSdkVersion and targetSdkVersion stored and used? What about build version?

What is minSdkVersion used for? targetSdkVersion?

What version of Android do we typically target? Why?

##7. UI Fragments and the Fragment Manager

Give an example of a UI design where activities are not a good solution (i.e. a design where fragments are a good solution). (Pictures are great for this, btw.)

Why are add/remove fragment operations grouped in transactions?

If I fire up the following activity and rotate the screen twice, how many times is the log statement printed out?

    public abstract class MyFragmentActivity extends FragmentActivity {
        @Override
        public void onCreate(Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_fragment);
            FragmentManager manager = getSupportFragmentManager();
            Fragment fragment = manager.findFragmentById(R.id.fragmentContainer);

            if (fragment == null) {
                Log.i(TAG, "Creating a new fragment");
                fragment = new MyFragment();
                manager.beginTransaction()
                    .add(R.id.fragmentContainer, fragment)
                    .commit();
            }
        }
    }

Which Fragment subclass should you use, and why?

##8. Layouts and Widgets

Give a quick explanation of FrameLayout, LinearLayout, and RelativeLayout.

What is the difference between a layout parameter and a regular attribute?

What is the difference between sp and dp?

Explain the steps in the layout process. How would I position a view at a specific X and Y coordinate in its parent view?

##9. Displaying Lists with ListFragment

In the AdapterView+Adapter relationship, what does the Adapter do?

What does the AdapterView do?

Why is it important that singletons in Android use the application context if they need to hold on to a context?

Why do we set focusable to false on the checkbox in the list row in the example from the book? What happens if you don't? Why?

##10. Using Fragment Arguments

In Chapter 5, we passed data to a second activity in extras. A fragment can access its activity's intent extras, too, so you could pass data in the exact same way. Why is this a bad idea?

When will setArguments throw an exception?

##11. Using ViewPager

What is the difference between FragmentPagerAdapter and FragmentStatePagerAdapter?

Explain when each of the following PagerAdapter methods are called by ViewPager:

    instantiateItem(ViewGroup, int)
    destroyItem(ViewGroup, int, Object)
    getCount()
    isViewFromObject(View, Object)

##12. Dialogs

Why should a Dialog be wrapped in a DialogFragment?

How do I pass data from a DialogFragment back to a calling fragment?

##13. Audio Playback Using MediaPlayer

What does MediaPlayer.release() do? When and why should you call it?

##14. Retained Fragments

What does setRetainInstance(true) do?

Calling setRetainInstance(true) solves some of the same persistence problems as onSaveInstanceState(Bundle). Name a problem that onSaveInstanceState(Bundle) solves, but setRetainInstance(true) does not solve.

##15. Localization

Explain how Android determines which resource to use. What if multiple resources match the current configuration?

##16. The Action Bar

What code do you need to write to display and respond to an action bar item? (exact method names not important)

What is the difference between temporal navigation and hierarchical/ancestral navigation? 

What does FLAG\_ACTIVITY\_CLEAR\_TOP do? NavUtils.navigateUpFromSameTask(Activity)?

##17. Saving and Loading Local Files

Where do your apps local files live? How do you usually access that location?

##18. Context Menus And Contextual Action Mode

What code do you need to write to display and respond to a context menu? (exact method names not important)

What is AdapterContextMenuInfo for? Why does ListView use it?

What is an Action Mode?

What do each of these methods on MultiChoiceModeListener do?

    public boolean onCreateActionMode(ActionMode mode, Menu menu) 
    public void onItemCheckedStateChanged(ActionMode mode, int position, long id, boolean checked) 
    public boolean onActionItemClicked(ActionMode mode, MenuItem item) 
    public boolean onPrepareActionMode(ActionMode mode, Menu menu) 
    public void onDestroyActionMode(ActionMode mode) 

Explain the fallback compatibility strategy and the duplication strategy. Give examples of each.

Explain briefly what ActionBarSherlock is.

##19. Camera I: Viewfinder

What is uses-permission for (in the context of the camera)? What about uses-feature?

What is a Surface? What is a SurfaceView? What is the SurfaceHolder for?

What sizes are valid parameters for Camera.setPreviewSize?

##20. Camera II: Taking Pictures And Handling Images

Why do we call Bitmap.recycle() when we're done with a Bitmap?

A student asks you this question: 

"I am writing an app that downloads and displays a lot of large images. How can I be sure that BitmapFactory.decodeFile(String, Options) never throws an OOM exception?"

What is your answer?

##21. Implicit Intents

What makes an intent "implicit"?

What is an action? A category? Data? What parts does data break down into?

What is an intent filter? Explain matching of actions and categories.

Let's say I run the following code:

    Intent i = new Intent(Intent.ACTION_VIEW);
    i.addCategory(Intent.CATEGORY_BROWSABLE);
    startActivity(i);

Give the simplest possible intent filter that would cause my activity to show up as an option when this intent is fired.

##22. Two-Pane Master-Detail Interfaces

What is an alias resource?

What is the role of the activity in a multi-fragment interface?

##23. More About Intents And Tasks

What is a task?

What is a process in Android? How are processes related to tasks (if at all)?

What does FLAG\_ACTIVITY\_NEW\_TASK do? Where on my Android phone can I see this flag in action?

##24. Styles And Includes

What is a style?

Explain the merge tag. What is it useful for?

##25. XML Drawables And 9-Patches

What is a Drawable?

What is an XML drawable?

What is a 9 patch?

##26. HTTP & Background Tasks

What happens if you perform networking on the main thread in Honeycomb and later?

What is a message loop? What happens if you perform a long-running task within the message loop?

Explain what each override of AsyncTask does:

    onPreExecute
    doInBackground
    onProgressUpdate
    onPostExecute

##27. Loopers, Handlers, and HandlerThread

What is a Handler? A Message? How do they relate to the Looper?

Explain how a thumbnail image is downloaded in PhotoGallery, starting with the adapter's getView and going all the way to onThumbnailDownloaded.

A student asks you this question:

"This stuff about Handlers seems really complicated. Why should I bother using them?"

What is your response?

##28. Search

What makes an activity "searchable"?

How is the system search dialog displayed?

What is a launch mode? How does singleTop launch mode change activity startup?

##29. Background Services

What is a Service?

What is an IntentService? Why do we recommend subclassing IntentService rather than Service?

In our code, we test for background networking in two different ways. Why?

What is the result of running the following code:

    Intent i1 = new Intent(Intent.ACTION_SEND);

    PendingIntent pi1 = PendingIntent.getActivity(getActivity(), 0, i1, 0);

    Intent i2 = new Intent(Intent.ACTION_SEND);

    PendingIntent pi2 = PendingIntent.getActivity(getActivity(), 0, i2, 0);
    
    pi1.cancel();

    pi2.send();

Why would a developer prefer to use AlarmManager.setInexactRepeating() instead of setRepeating()?

A designer asks you to implement a notification with a progress bar that is updated as a large file download proceeds. How would you update your notification to show the new progress value after it was initially posted?

##30. Broadcast Intents

When would you want to use a standalone broadcast receiver over a dynamic receiver? Vice versa?

What is the most important benefit of using an ordered broadcast receiver?

What do broadcast receivers give you that conventional Java communication mechanisms don't?

##31. Browsing The Web And WebView

What are the four interfaces used to extend and/or customize WebView?

##32. Custom Views And Touch Events

Briefly describe how an Android view hierarchy is drawn to the screen. 

How do I cause a view hierarchy to redraw itself?

How do you receive touch events? What type of touch events are there?

##33. Tracking The Device's Location

What is a location provider? 

What is a Criteria for?

Let's say that you are tasked with writing an application that uses GPS when available, but falls back on cell tower location when it is not. In broad terms, what would you have to do to implement this?

##34. Local Databases With SQLite

What does SQLiteOpenHelper do?

What is the nullColumnHack parameter on SqliteDatabase.insert() for?

##35. Loaders

What are loaders used for?

What are the major lifecycle events on a loader?

What about for a loader's client (i.e. LoaderCallbacks)?

##36. Maps

Where does the Maps API v2 live?

Hey, can I just use the API key from the solutions? Why/why not?


