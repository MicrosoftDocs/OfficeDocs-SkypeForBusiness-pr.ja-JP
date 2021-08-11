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
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig には、1 行に一部の常設チャット サーバーでサポートされていない構成が含まれている。
ms.openlocfilehash: 0e9cc0a0c4686432032591aa0c380b303fc5251a56a6c983a1e10b009e0eb28a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278355"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig には、1 行に一部の常設チャット サーバーでサポートされていない構成が含まれている。
  
**Columns**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|configLabel  <br/> |NULL でない nvarchar (255)  <br/> |"プール" を含みます。  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |構成の内容です。  <br/> |
|configPoolID  <br/> |NULL でない GUID  <br/> |データベース インスタンスの一意の識別子。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|configLabel  <br/> |主キー。  <br/> |
   

