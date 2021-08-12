---
title: 既存の会議および会議コンテンツの移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ユーザー アカウントを 2019 サーバーから 2019 Skype for Business Serverに移動すると、そのユーザー アカウントで次の情報が移動されます。
ms.openlocfilehash: e28cbce30608672d27578cfaa5ab92dbe1ed3c4cd6b234da7389b1f9a6978350
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312301"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>既存の会議および会議コンテンツの移行

ユーザー アカウントが 2019 年 2019 年のサーバーに移動Skype for Business Server、そのユーザー アカウントで次の情報が移動されます。
  
- **そのユーザーがスケジュールした会議**。電話会議ディレクトリおよび電話会議データも移動されます。
    
- **ユーザーの個人識別番号 (PIN)** です。 ユーザーの現在の PIN は、有効期限が切れるか、新しい PIN を要求するまで引き続き機能します。
    
次に示すユーザー アカウント情報は、新しいサーバーに移動されません。
  
- **会議コンテンツ**。 会議中に共有されるコンテンツ (PowerPoint、ホワイトボード、添付ファイル、ポーリング データなど) を移動するには **、Move-CsUser** コマンドレットの一部として **-MoveConferenceData** パラメーターを使用します。 
    

