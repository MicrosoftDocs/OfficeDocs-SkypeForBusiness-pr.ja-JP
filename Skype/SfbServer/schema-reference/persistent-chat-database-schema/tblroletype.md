---
title: tblRoleType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType は、役割の種類とそれに関連付けられたアクセス許可セットを含む静的参照テーブルです。
ms.openlocfilehash: 888628c1aca01e90694ed946569a81b1b7394b95
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812905"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType は、役割の種類とそれに関連付けられたアクセス許可セットを含む静的参照テーブルです。
  
**行**

|**列**|**種類**|**説明**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int (null ではない)  <br/> |役割の種類 ID。  <br/> |
|rtypeDesc  <br/> |nvarchar (256)、null ではない  <br/> | 役割の種類の説明。 次の4つの役割を使用できます。 <br/>  メンバー: チャットルームのメンバー <br/>  管理職: チャットルームマネージャー <br/>  読み上げ: 聴衆チャットルームの発表者 <br/>  作成者: チャットルームを作成できる <br/> |
|rtypeAllowedPermSet  <br/> |bigint (null ではない)  <br/> | ロールの権限セット。 使用されるビットは次のとおりです。 <br/>  2: 役割がノードを管理できる場合は True。 <br/>  4: 役割で子ノードを作成できる場合は True です。 <br/>  7: 役割がチャットルーム (または、カテゴリの子チャットルーム) に参加できる場合は True。 <br/>  8: 役割がチャットルーム (または、カテゴリの子チャットルーム) でチャットできる場合は True。 <br/>  10: 役割がチャットルームに参加していないときでもチャット履歴を読むことができる場合は True。 <br/>  11: 役割がチャットルームを表示できる場合は True です。 (これは、スコープや可視性などの要因によってさらに改良されています)。 <br/>  12: この役割が聴衆チャットルームでチャットできる場合は True です。 <br/>  13: ノードを表示したときに、役割が可視性規則を無視できる場合は True です。 <br/> |
   
**Key**

|**列**|**説明**|
|:-----|:-----|
|rtypeID  <br/> |主キー。  <br/> |
   

