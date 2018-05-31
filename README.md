This repository demonstrates an error when trying to use the System.Drawing.Common NuGet package in an AWS Lambda function built using .NET Core 2.0

	> {
	  "errorType": "TypeInitializationException",
	  "errorMessage": "The type initializer for 'Gdip' threw an exception.",
	  "stackTrace": [
		"at System.Drawing.SafeNativeMethods.Gdip.GdipCreateBitmapFromScan0(Int32 width, Int32 height, Int32 stride, Int32 format, HandleRef scan0, IntPtr& bitmap)",
		"at System.Drawing.Bitmap..ctor(Int32 width, Int32 height, PixelFormat format)",
		"at TestFailExample.Function.FunctionHandler(String input, ILambdaContext context) in C:\\work\\graphics\\TestFailExample\\Function.cs:line 25",
		"at lambda_method(Closure , Stream , Stream , LambdaContextInternal )"
	  ],
	  "cause":   {
		"errorType": "DllNotFoundException",
		"errorMessage": "Unable to load DLL 'libdl': The specified module or one of its dependencies could not be found.\n (Exception from HRESULT: 0x8007007E)",
		"stackTrace": [
		  "at Interop.Libdl.dlopen(String fileName, Int32 flag)",
		  "at System.Drawing.SafeNativeMethods.Gdip.LoadNativeLibrary()",
		  "at System.Drawing.SafeNativeMethods.Gdip..cctor()"
		]
	  }
	}