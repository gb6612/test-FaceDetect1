Face Detect in Visual Studio(VS)

Packages needed:
AForge.Net = access video
EMGU.CV = cross platform .Net wrapper to the OpenCV image processing library

Create a project under VS
In the solution explorer right-click the project -> manage NuGet packages -> Browse
Search & Install AForge + Emgu.CV + Emgu.CV.Bitmap + Emgu.CV.runtime.windows

In solution explorer check under References that the following was added:
AForge.Video
AForge.Video.DirectShow
AForge.Video.Controls

In the Toolbox window, check that a AForge.NET form container was added.

In your form, add toolbox AForge.NET - VideoSourcePlayer

In the code add:
using AForge.Video;
using AForge.Video.DirectShow;
using Emgu.CV;
using Emgu.CV.CvEnum;
using Emgu.CV.Structure;



To open a video device:
            VideoCaptureDeviceForm form = new VideoCaptureDeviceForm();

            if (form.ShowDialog(this) == DialogResult.OK)
            {
                // create video source
                VideoCaptureDevice videoSource = form.VideoDevice;

                // open it
                OpenVideoSource(videoSource);
            }

