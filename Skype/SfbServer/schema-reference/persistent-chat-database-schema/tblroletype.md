---
title: tblRoleType
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType は静的な検索テーブルであり、役割の種類とそれに関連付けられたアクセス許可のセットが格納されています。
ms.openlocfilehash: f1e224857d7c5b427176d786fc87b28206419bfa
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745733"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType は静的な検索テーブルであり、役割の種類とそれに関連付けられたアクセス許可のセットが格納されています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|rtypeID  <br/> |NULL でない int  <br/> |役割の種類の ID。  <br/> |
|rtypeDesc  <br/> |NULL でない nvarchar (256)  <br/> | 役割の種類の説明。使用できる役割は次の 4 つです。 <br/>  メンバー: チャット ルームのメンバー <br/>  マネージャー: チャット ルームのマネージャー <br/>  承認されたメンバー: 大会議室のチャット ルームの発表者 <br/>  作成者: チャット ルームの作成者 <br/> |
|rtypeAllowedPermSet  <br/> |NULL でない bigint  <br/> | 役割のアクセス許可セット。使用されるビットは次のとおりです。 <br/>  2: 役割がノードを管理できる場合は True。 <br/>  4: 役割が子ノードを作成できる場合は True。 <br/>  7: 役割がチャット ルーム (またはカテゴリの子チャット ルーム) に参加できる場合は True。 <br/>  8: 役割がチャット ルーム (またはカテゴリの子チャット ルーム) でチャットできる場合は True。 <br/>  10: 役割がチャット ルームに参加していなくてもチャットの履歴を読むことができる場合は True。 <br/>  11: 役割がチャット ルームを見ることができる場合は True (これはスコープや可視性などの要素によってさらに微調整されます)。 <br/>  12: 役割が大会議室のチャット ルームでチャットできる場合は True。 <br/>  13: 役割がノードを表示するときに可視性ルールをバイパスできる場合は True。 <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|rtypeID  <br/> |主キー。  <br/> |
   

