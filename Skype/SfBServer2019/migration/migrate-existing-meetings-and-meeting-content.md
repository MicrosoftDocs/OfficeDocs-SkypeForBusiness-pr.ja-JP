---
title: 既存の会議および会議コンテンツの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ユーザーアカウントを Skype for Business Server 2019 サーバーに移動すると、次の情報がそのユーザーアカウントに移動されます。
ms.openlocfilehash: 6394ebf798560ce5a13fe7ba931076364257decc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813475"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>既存の会議および会議コンテンツの移行

ユーザーアカウントを Skype for Business Server 2019 サーバーに移動すると、次の情報がそのユーザーアカウントで移動されます。
  
- **ユーザーが既にスケジュールした会議**。 これには、会議ディレクトリと会議データの移動が含まれます。
    
- **ユーザーの暗証番号 (PIN)**。 ユーザーの現在の PIN は、有効期限が切れるか、ユーザーが新しい PIN を要求するまで、引き続き動作します。
    
次のユーザーアカウント情報は、新しいサーバーに移動されません。
  
- **会議コンテンツ**。 会議中に共有されたコンテンツ (PowerPoint、ホワイトボード、添付ファイル、投票データなど) を移動するには、 **move-CsUser**コマンドレットの一部として、 **-moveconの [data** ] パラメーターを使用します。 
    

