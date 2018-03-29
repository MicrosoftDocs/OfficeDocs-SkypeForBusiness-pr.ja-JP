---
title: FileTransfers ビュー
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTranfer ビューでは、ピア ツー ピア ファイル転送セッションに関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 69b986c24a3a8f3646738eb3e1e3e97794be8e9e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="filetransfers-view"></a>FileTransfers ビュー
 
FileTranfer ビューでは、ピア ツー ピア ファイル転送セッションに関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
> [!NOTE]
> FileTransfers ビューが含まれていますすべて[SessionDetails ビュー](sessiondetails-0.md)内の列のさらに以下の列には。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**ファイル名** <br/> |nvarchar(256)  <br/> |ファイルの名前が転送されます。  <br/> |
|**クッキー** <br/> |nvarchar (128)  <br/> |この 1 つに関連付けられたすべてのフォロー アップ メッセージを識別する場合に使用されます。  <br/> |
|**FileIdentity** <br/> |一意識別子  <br/> |同じ名前のファイルに関連するファイル転送の間で区別するために一意の識別子です。  <br/> |
|**受け入れる** <br/> |bit  <br/> |真または NULL にすることができます。 TRUE の場合、[元に戻すし、[キャンセル] が NULL になります。  <br/> |
|**元に戻す** <br/> |bit  <br/> |真または NULL にすることができます。 TRUE の場合、[受信を許可し、[キャンセル] NULL になります。  <br/> |
|**キャンセル** <br/> |bit  <br/> |真または NULL にすることができます。 TRUE の場合、[承認および却下 NULL になります。  <br/> |
   

