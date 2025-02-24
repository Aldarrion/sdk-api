---
UID: NF:wmp.IWMPPlaylist.get_isIdentical
title: IWMPPlaylist::get_isIdentical (wmp.h)
description: The get_isIdentical method retrieves a value indicating whether the specified playlist is identical to the current playlist.helpviewer_keywords: ["IWMPPlaylist interface [Windows Media Player]","get_isIdentical method","IWMPPlaylist.get_isIdentical","IWMPPlaylist::get_isIdentical","IWMPPlaylistget_isIdentical","get_isIdentical","get_isIdentical method [Windows Media Player]","get_isIdentical method [Windows Media Player]","IWMPPlaylist interface","wmp.iwmpplaylist_get_isidentical","wmp/IWMPPlaylist::get_isIdentical"]
old-location: wmp\iwmpplaylist_get_isidentical.htm
tech.root: WMP
ms.assetid: 480fa108-5cfd-49ab-92fe-c635f13f3194
ms.date: 12/05/2018
ms.keywords: IWMPPlaylist interface [Windows Media Player],get_isIdentical method, IWMPPlaylist.get_isIdentical, IWMPPlaylist::get_isIdentical, IWMPPlaylistget_isIdentical, get_isIdentical, get_isIdentical method [Windows Media Player], get_isIdentical method [Windows Media Player],IWMPPlaylist interface, wmp.iwmpplaylist_get_isidentical, wmp/IWMPPlaylist::get_isIdentical
f1_keywords:
- wmp/IWMPPlaylist.get_isIdentical
dev_langs:
- c++
req.header: wmp.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows Media Player 9 Series or later.
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
req.lib: 
req.dll: Wmp.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- wmp.dll
api_name:
- IWMPPlaylist.get_isIdentical
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
---

# IWMPPlaylist::get_isIdentical


## -description



The <b>get_isIdentical</b> method retrieves a value indicating whether the specified playlist is identical to the current playlist.




## -parameters




### -param pIWMPPlaylist [in]

Pointer to an <b>IWMPPlaylist</b> interface for the playlist that this method compares to the current playlist.


### -param pvbool [out]

<b>VARIANT_BOOL</b> that specifies whether the compared playlists were identical.


## -returns



The method returns an <b>HRESULT</b>. Possible values include, but are not limited to, those in the following table.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method succeeded.

</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/wmp/nn-wmp-iwmpplaylist">IWMPPlaylist Interface</a>
 

 

