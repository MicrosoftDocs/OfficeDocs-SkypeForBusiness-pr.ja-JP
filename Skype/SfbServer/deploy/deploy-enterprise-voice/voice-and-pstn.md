---
title: 音声ポリシー、PSTN 使用法レコード、および音声ルートを構成Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: '概要: 音声ポリシー、PSTN 使用法レコード、および音声ルートを構成する方法について説明します。Skype for Business Server。'
---

# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a>音声ポリシー、PSTN 使用法レコード、および音声ルートを構成Skype for Business
 
**概要:** 音声ポリシー、PSTN 使用法レコード、および音声ルートを構成する方法については、Skype for Business Server。
  
音声ポリシー、PSTN 使用法レコード、およびボイス ルートは、一体的に関わり合っています。 音声ポリシーは、一連の通話機能を選択し、PSTN 使用法レコードのセット (音声ポリシーを割り当てられるユーザーまたはグループを対象に、承認される権限を指定します) にポリシーを割り当てることで、構成します。 PSTN 使用法レコードは、ボイス ルートにも割り当てられます。これにより、ルートとこの PSTN 使用法レコードの使用を許可されたユーザーが照合されます。 つまり、ユーザーはルートと一致する PSTN 使用法レコードが割り当てられている場合のみ、そのルートに電話をかけることができます。
  
新しいエンタープライズ VoIP を展開する場合の推奨ワークフローは、最初に該当する PSTN 使用法レコードを含む音声ポリシーを構成し、次に、該当するルートを各 PSTN 使用法レコードに割り当てることです。 
  
> [!NOTE]
> また、ユーザー スコープを使用して音声ポリシーを  *作成*  し、個々のユーザーまたはグループに割り当てすることもできます。
  
これらの各タスクを実行するための詳細ステップについては、このセクションの手順を参照してください。
  
## <a name="in-this-section"></a>このセクションの内容

- [音声ポリシーを作成または変更し、音声ポリシーで PSTN 使用法レコードを構成Skype for Business](voice-policy-and-pstn-usage-records.md)
    
- [ボイス メール エスケープを構成Skype for Business](configure-voice-mail-escape.md)
    
- [[PSTN 使用法レコードの表示] Skype for Business](view-pstn-usage-records.md)
    
- [音声ルートを作成または変更Skype for Business](create-or-modify-a-voice-route.md)
    
- [音声ルート構成ファイルをエクスポートまたはインポートSkype for Business](voice-route-configuration-import-export.md)
    
- [音声ルーティング構成に保留中の変更を公開Skype for Business](voice-route-config-changes.md)
    

