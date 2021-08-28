---
title: tblConfig
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig には、1 行に一部の常設チャット サーバーでサポートされていない構成が含まれている。
ms.openlocfilehash: 8cf1fc53087d3fc786ac47e848a21dbd2a8f5549
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595309"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig には、1 行に一部の常設チャット サーバーでサポートされていない構成が含まれている。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|configLabel  <br/> |NULL でない nvarchar (255)  <br/> |"プール" を含みます。  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |構成の内容です。  <br/> |
|configPoolID  <br/> |NULL でない GUID  <br/> |データベース インスタンスの一意の識別子。  <br/> |
   
**Key**

|**列**|**説明**|
|:-----|:-----|
|configLabel  <br/> |主キー。  <br/> |
   

