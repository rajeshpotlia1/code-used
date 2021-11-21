% Simple spectroscope script - imports image and converts to intensity vs. <br>
% wavelength

% Rajesh Potlia, 20/11/2021

%---Import JPG Image <br>
    raw_image=imread('20211120_151019.jpg');  %import JPG image <br>
    %raw_image=imread('incandescent.jpg');  %import JPG image  <br> 
    raw_image=double(raw_image); <br>
    

%---Add up 3 color channels <br>
    total_intensity=raw_image(:,:,1)+raw_image(:,:,2)+raw_image(:,:,3); <br>
    figure(1) <br>
    pcolor(total_intensity), shading flat, colormap(gray) <br>
    figure(2) <br>
    plot(mean(total_intensity(100:120,:,:))) <br>
    dbstop if error ;
