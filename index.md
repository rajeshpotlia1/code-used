% Simple spectroscope script - imports image and converts to intensity vs.
% wavelength

% Rajesh Potlia, 20/11/2021

%---Import JPG Image
    raw_image=imread('20211120_151019.jpg');  %import JPG image
    %raw_image=imread('incandescent.jpg');  %import JPG image    
    raw_image=double(raw_image);
    

%---Add up 3 color channels
    total_intensity=raw_image(:,:,1)+raw_image(:,:,2)+raw_image(:,:,3);
    figure(1)
    pcolor(total_intensity), shading flat, colormap(gray)
    figure(2)
    plot(mean(total_intensity(100:120,:,:)))
    dbstop if error ;
