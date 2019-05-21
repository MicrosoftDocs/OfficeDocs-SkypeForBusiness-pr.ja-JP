---
title: 既存の会議および会議コンテンツの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ユーザーアカウントを Skype for Business Server 2019 サーバーに移動すると、次の情報がそのユーザーアカウントに移動されます。
ms.openlocfilehash: 4b5c7981374f3e2bf6dc2d87a0b21d972ddb14ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288601"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>既存の会議および会議コンテンツの移行

ユーザーアカウントを Skype for Business Server 2019 サーバーに移動すると、次の情報がそのユーザーアカウントで移動されます。
  
- **ユーザーが既にスケジュールした会議**。 これには、会議ディレクトリと会議データの移動が含まれます。
    
- **ユーザーの暗証番号 (PIN)**。 ユーザーの現在の PIN は、有効期限が切れるか、ユーザーが新しい PIN を要求するまで、引き続き動作します。
    
次のユーザーアカウント情報は、新しいサーバーに移動されません。
  
- **会議コンテンツ**。 会議中に共有されたコンテンツ (PowerPoint、ホワイトボード、添付ファイル、投票データなど) を移動するには、 **move-CsUser**コマンドレットの一部として、 **-moveconの [data** ] パラメーターを使用します。 
    

