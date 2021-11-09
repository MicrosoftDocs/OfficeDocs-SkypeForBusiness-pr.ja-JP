---
title: tblConfig
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: ddfd8cdc48158a3f4b2776b80c0bf0293ecff71b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846290"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig には、1 行に一部の常設チャット サーバーでサポートされていない構成が含まれている。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|configLabel  <br/> |NULL でない nvarchar (255)  <br/> |"プール" を含みます。  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |構成の内容です。  <br/> |
|configPoolID  <br/> |NULL でない GUID  <br/> |データベース インスタンスの一意の識別子。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|configLabel  <br/> |主キー。  <br/> |
   

