---
title: Skype for Business で音声ポリシー、PSTN 使用状況レコード、および音声ルートを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: '概要: Skype for Business Server でボイスポリシー、PSTN 使用状況レコード、および音声ルートを構成する方法について説明します。'
ms.openlocfilehash: 5ce6b6b3e93804f648529043b9189110d25cbb08
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300910"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a>Skype for Business で音声ポリシー、PSTN 使用状況レコード、および音声ルートを構成する
 
**概要:** Skype for Business Server でボイスポリシー、PSTN 使用状況レコード、および音声ルートを構成する方法について説明します。
  
音声ポリシー、PSTN 使用法レコード、およびボイス ルートは、一体的に関わり合っています。音声ポリシーは、一連の通話機能を選択し、PSTN 使用法レコードのセット (音声ポリシーを割り当てられるユーザーまたはグループを対象に、承認される権限を指定します) にポリシーを割り当てることで、構成します。PSTN 使用法レコードは、ボイス ルートにも割り当てられます。これにより、ルートとこの PSTN 使用法レコードの使用を許可されたユーザーが照合されます。つまり、ユーザーはルートと一致する PSTN 使用法レコードが割り当てられている場合のみ、そのルートに電話をかけることができます。
  
新しいエンタープライズ VoIP を展開する場合の推奨ワークフローは、最初に該当する PSTN 使用法レコードを含む音声ポリシーを構成し、次に、該当するルートを各 PSTN 使用法レコードに割り当てることです。 
  
> [!NOTE]
> また、*ユーザー*のスコープを使用して音声ポリシーを作成し、個々のユーザーまたはグループに割り当てることもできます。
  
これらの各タスクを実行するための詳細ステップについては、このセクションの手順を参照してください。
  
## <a name="in-this-section"></a>このセクションの内容

- [Skype for Business で音声ポリシーを作成または変更し、PSTN 使用状況レコードを構成する](voice-policy-and-pstn-usage-records.md)
    
- [Skype for Business でボイスメールのエスケープを設定する](configure-voice-mail-escape.md)
    
- [Skype for Business での PSTN 使用状況レコードの表示](view-pstn-usage-records.md)
    
- [Skype for Business での音声ルートの作成または変更](create-or-modify-a-voice-route.md)
    
- [Skype for Business のボイスルート構成ファイルをエクスポートまたはインポートする](voice-route-configuration-import-export.md)
    
- [Skype for Business の音声ルーティング構成に保留中の変更を公開する](voice-route-config-changes.md)
    

