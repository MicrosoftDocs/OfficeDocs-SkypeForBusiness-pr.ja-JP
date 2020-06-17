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
description: ユーザーアカウントを Skype for Business Server 2019 サーバーに移動すると、そのユーザーアカウントを使用して次の情報が移動されます。
ms.openlocfilehash: 6513f581f55028ec28d4cf05f1f1b3df37c49e65
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752689"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>既存の会議および会議コンテンツの移行

ユーザーアカウントが Skype for Business Server 2019 サーバーに移動されると、そのユーザーアカウントを使用して次の情報が移動されます。
  
- **そのユーザーがスケジュールした会議**。 電話会議ディレクトリおよび電話会議データも移動されます。
    
- **ユーザーの暗証番号 (PIN)**。 ユーザーの現在の PIN は、期限が切れるか、ユーザーが新しい PIN を要求するまで引き続き機能します。
    
次に示すユーザー アカウント情報は、新しいサーバーに移動されません。
  
- **会議コンテンツ**。 PowerPoint、ホワイトボード、添付ファイル、投票データなど、会議中に共有されるコンテンツを移動するには、 **-moveconferencedata**パラメーターを、 **csuser**コマンドレットの一部として使用します。 
    

