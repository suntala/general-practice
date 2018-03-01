//assuming existence of a giveColor func 
const giveColor = (pixelCoordinates) => { 
    // return color of pixel
}

//pixelObject = {x: __, y: __, color: __}
//pictureDim = {width: __, height: __}
const fillShape = (pixelObject, newColor, firstPix, pictureDim) => {
    let origColor = firstPix.color;

    let surroundingCoo = [ 
        [pixelObject.x + 1, pixelObject.y], 
        [pixelObject.x - 1, pixelObject.y],
        [pixelObject.x, pixelObject.y + 1],
        [pixelObject.x, pixelObject.y - 1]
    ]

    // cooArray = [horCoo, vertCoo]
    const makePixelObj = cooArray => {  
        return {x: cooArray[0], y: cooArray[1], color: giveColor(cooArray[0], cooArray[1])}
    }

    const checkBelongsInShape =  pixelObj => {
        if (pixelObj.x > pictureDim.width 
            || pixelObj.x < 0
            || pixelObj.y > pictureDim.height 
            || pixelObj.y < 0
            || pixelObj.color !== origColor
        ) {
            return false
        } else {
            return true
        }
    }

    const checkEdge = pixelObj => {      
        return surroundingCoo.map(!checkBelongsInShape)
    }

    
    if (!checkBelongsInShape(pixelObject)) { 
        return
    }
    else if (checkEdge().length) {
        surroundingCoo.map(makePixelObj).filter(checkBelongsInShape).map(fillShape)
    }
    else {
        pixelObject.color = newColor;
        surroundingCoo.map(makePixelObj).map(fillShape)
    }
}
