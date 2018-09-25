#target photoshop

app.bringToFront();

var activeDoc = app.activeDocument;

var myPathItem = activeDoc.pathItems.getByName("CLIPPING");

myPathItem.select();
myPathItem.makeSelection(0.3);
app.activeDocument.selection.invert();

makeLayerMask('HdSl');

function makeLayerMask(maskType) {
if( maskType == undefined) maskType = 'RvlS' ; //from selection
//requires a selection 'RvlS'  complete mask 'RvlA' otherThanSelection 'HdSl'
    var desc140 = new ActionDescriptor();
    desc140.putClass( charIDToTypeID('Nw  '), charIDToTypeID('Chnl') );
        var ref51 = new ActionReference();
        ref51.putEnumerated( charIDToTypeID('Chnl'), charIDToTypeID('Chnl'), charIDToTypeID('Msk ') );
    desc140.putReference( charIDToTypeID('At  '), ref51 );
    desc140.putEnumerated( charIDToTypeID('Usng'), charIDToTypeID('UsrM'), charIDToTypeID(maskType) );
    executeAction( charIDToTypeID('Mk  '), desc140, DialogModes.NO );
}

var filePath = activeDocument.fullName.path;  
SavePNG("/users/robfuncken/development/temp.png");

function SavePNG(saveFile){

  var opts = new ExportOptionsSaveForWeb();
    opts.format = SaveDocumentType.PNG;
    opts.PNGB = true;
    opts.quality = 100;
    pngFile = new File(saveFile);
    opts.includeProfile = true;
    app.activeDocument.exportDocument(pngFile, ExportType.SAVEFORWEB, opts);
}
