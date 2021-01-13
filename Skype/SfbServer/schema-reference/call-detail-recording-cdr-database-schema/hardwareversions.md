---
title: Skype for Business Server 2015 の HardwareVersions テーブル
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
ms.assetid: ca05582b-082c-4bab-9233-36fc9434dbca
description: HardwareVersions テーブルはサポート テーブルです。 各レコードには、1 つのデバイス ハードウェア バージョンに関する情報が格納されます。
ms.openlocfilehash: 2b9ac6b31f0af30e896d2943eaa4065aecdd4de3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821577"
---
# <a name="hardwareversions-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の HardwareVersions テーブル
 
HardwareVersions テーブルはサポート テーブルです。 各レコードには、1 つのデバイス ハードウェア バージョンに関する情報が格納されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |Primary  <br/> |このハードウェア バージョンを識別する一意の番号。  <br/> |
|**バージョン** <br/> |nvarchar(256)  <br/> | <br/> |ハードウェア バージョン。  <br/> |
   

