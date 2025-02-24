---
UID: NF:mediaobj.IMediaObject.GetInputSizeInfo
title: IMediaObject::GetInputSizeInfo (mediaobj.h)
description: The GetInputSizeInfo method retrieves the buffer requirements for a specified input stream.helpviewer_keywords: ["GetInputSizeInfo","GetInputSizeInfo method [DirectShow]","GetInputSizeInfo method [DirectShow]","IMediaObject interface","IMediaObject interface [DirectShow]","GetInputSizeInfo method","IMediaObject.GetInputSizeInfo","IMediaObject::GetInputSizeInfo","IMediaObjectGetInputSizeInfo","dshow.imediaobject_getinputsizeinfo","mediaobj/IMediaObject::GetInputSizeInfo"]
old-location: dshow\imediaobject_getinputsizeinfo.htm
tech.root: DirectShow
ms.assetid: cce6359a-cd6e-46c9-a1cb-553ae5f83b9c
ms.date: 12/05/2018
ms.keywords: GetInputSizeInfo, GetInputSizeInfo method [DirectShow], GetInputSizeInfo method [DirectShow],IMediaObject interface, IMediaObject interface [DirectShow],GetInputSizeInfo method, IMediaObject.GetInputSizeInfo, IMediaObject::GetInputSizeInfo, IMediaObjectGetInputSizeInfo, dshow.imediaobject_getinputsizeinfo, mediaobj/IMediaObject::GetInputSizeInfo
f1_keywords:
- mediaobj/IMediaObject.GetInputSizeInfo
dev_langs:
- c++
req.header: mediaobj.h
req.include-header: Dmo.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Dmoguids.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Dmoguids.lib
- Dmoguids.dll
api_name:
- IMediaObject.GetInputSizeInfo
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
---

# IMediaObject::GetInputSizeInfo


## -description



The <code>GetInputSizeInfo</code> method retrieves the buffer requirements for a specified input stream.




## -parameters




### -param dwInputStreamIndex

Zero-based index of an input stream on the DMO.


### -param pcbSize [out]

Pointer to a variable that receives the minimum size of an input buffer for this stream, in bytes.


### -param pcbMaxLookahead [out]

Pointer to a variable that receives the maximum amount of data that the DMO will hold for lookahead, in bytes. If the DMO does not perform lookahead on the stream, the value is zero.


### -param pcbAlignment [out]

Pointer to a variable that receives the required buffer alignment, in bytes. If the input stream has no alignment requirement, the value is 1.


## -returns



Returns an <b>HRESULT</b> value. Possible values include those in the following table.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>DMO_E_INVALIDSTREAMINDEX</b></dt>
</dl>
</td>
<td width="60%">
Invalid stream index.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>DMO_E_TYPE_NOT_SET</b></dt>
</dl>
</td>
<td width="60%">
Media type was not set.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
Success.

</td>
</tr>
</table>
 




## -remarks



The buffer requirements may depend on the media types of the various streams. Before calling this method, set the media type of each stream by calling the <a href="https://docs.microsoft.com/windows/desktop/api/mediaobj/nf-mediaobj-imediaobject-setinputtype">IMediaObject::SetInputType</a> and <a href="https://docs.microsoft.com/windows/desktop/api/mediaobj/nf-mediaobj-imediaobject-setoutputtype">IMediaObject::SetOutputType</a> methods. If the media types have not been set, this method might return an error.

If the DMO performs lookahead on the input stream, it returns the DMO_INPUT_STREAMF_HOLDS_BUFFERS flag in the <a href="https://docs.microsoft.com/windows/desktop/api/mediaobj/nf-mediaobj-imediaobject-getinputstreaminfo">IMediaObject::GetInputStreamInfo</a> method. During processing, the DMO holds up to the number of bytes indicated by the <i>pcbMaxLookahead</i> parameter. The application must allocate enough buffers for the DMO to hold this much data.

A buffer is <i>aligned</i> if the buffer's start address is a multiple of <i>*pcbAlignment</i>. The alignment must be a power of two. Depending on the microprocessor, reads and writes to an aligned buffer might be faster than to an unaligned buffer. Also, some microprocessors do not support unaligned reads and writes.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/mediaobj/nn-mediaobj-imediaobject">IMediaObject Interface</a>
 

 

