 clc;
clear;
folder = 'C:\Users\NIKHIL\Desktop\images'
filePattern = fullfile(folder, '*.tif');
f=dir(filePattern)
files={f.name}
for k=1:numel(files)
	fullFileName = fullfile(folder, files{k})
	cellArrayOfImages{k}=imread(fullFileName)
end


for k=1:numel(files)
    I=cellArrayOfImages{k};
    
    res='C:\Users\NIKHIL\Desktop\images1'
    
    p=rgb2gray(I);
    
    y1=im2double(p);
    a=y1;b=y1;
    f=1;
    [r,c]=size(y1);

    for i=1:r
      for j=1:c
        b(i,j)=f*log(1+y1(i,j));  
      end
    end
    
    bi=b>0.2;
    d = zeros(130,130)
    c=imresize(bi,[130,130]);
    
    for m=1:130
        n=1:130
    d(m,n)=c(m,n);
    end
    
    baseFileName = sprintf('%d.png', k);  
    fullFileName = fullfile(res, baseFileName);  
    imwrite(c, fullFileName);    
end

folder1 = 'C:\Users\NIKHIL\Desktop\images1'
filePattern1 = fullfile(folder1, '*.png');
f1=dir(filePattern1)
files1={f1.name}
for q=1:numel(files1)
	fullFileName1 = fullfile(folder1, files1{q})
	cellArrayOfImages1{q}=imread(fullFileName1)
end

x=zeros(10)

for q=1:numel(files1)
    I1=cellArrayOfImages1{q};
    x(q)=wp(I1)                %  x() is the array of water percantages of every satellite image
end
       
function f=wp(o)
  f=(1-nnz(o)/numel(o))*100;
end
