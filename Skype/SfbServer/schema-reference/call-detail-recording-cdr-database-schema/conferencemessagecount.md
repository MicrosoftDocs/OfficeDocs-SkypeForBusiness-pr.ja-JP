---
title: Skype for Business Server 2015 の ConferenceMessageCount テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: このテーブル内の各レコードは、1人の IM 会議で1人のユーザーを表し、そのユーザーから送信されたメッセージの数が含まれます。 各会議は、この表の複数のレコードで表されます。ユーザーごとに1つのレコード。
ms.openlocfilehash: ef343536c34b3bd27d71ee37813e4b4e65156094
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296456"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の ConferenceMessageCount テーブル
 
このテーブル内の各レコードは、1人の IM 会議で1人のユーザーを表し、そのユーザーから送信されたメッセージの数が含まれます。 各会議は、この表の複数のレコードで表されます。ユーザーごとに1つのレコード。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**セッション Id** <br/> |datetime  <br/> |プライマリ、外部  <br/> |会議インスタンスの時刻。 電話会議インスタンスを一意に識別するために**Sessionidseq**と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 の会議の表](conferences.md)」を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |プライマリ、外部  <br/> |会議インスタンスを識別する ID 番号。 電話会議インスタンスを一意に識別するために**Sessionidtime**と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 の会議の表](conferences.md)」を参照してください。 <br/> |
|**UserId** <br/> |int  <br/> |外部  <br/> |[[ユーザー] テーブル](users.md)から参照されている、このユーザーを識別する一意の番号。  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |この会議中にこのユーザーによって送信されたメッセージの数です。  <br/> |
   

