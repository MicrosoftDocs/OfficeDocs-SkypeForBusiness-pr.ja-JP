---
title: Skype for Business で音声ポリシー、PSTN 使用法レコード、およびボイス ルートを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: '概要: Skype for Business Server で音声ポリシー、PSTN 使用法レコード、およびボイス ルートを構成する方法について説明します。'
ms.openlocfilehash: f8c9f75f24a06b210a1c17ed11a1485ab5158f3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830449"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a>Skype for Business で音声ポリシー、PSTN 使用法レコード、およびボイス ルートを構成する
 
**概要:** Skype for Business Server で音声ポリシー、PSTN 使用法レコード、およびボイス ルートを構成する方法について説明します。
  
音声ポリシー、PSTN 使用法レコード、およびボイス ルートは、一体的に関わり合っています。 音声ポリシーは、一連の通話機能を選択し、PSTN 使用法レコードのセット (音声ポリシーを割り当てられるユーザーまたはグループを対象に、承認される権限を指定します) にポリシーを割り当てることで、構成します。 PSTN 使用法レコードは、ボイス ルートにも割り当てられます。これにより、ルートとこの PSTN 使用法レコードの使用を許可されたユーザーが照合されます。 つまり、ユーザーはルートと一致する PSTN 使用法レコードが割り当てられている場合のみ、そのルートに電話をかけることができます。
  
新しいエンタープライズ VoIP を展開する場合の推奨ワークフローは、最初に該当する PSTN 使用法レコードを含む音声ポリシーを構成し、次に、該当するルートを各 PSTN 使用法レコードに割り当てることです。 
  
> [!NOTE]
> ユーザー スコープを使用して音声ポリシーを作成し、個々のユーザーまたはグループに割り当てすることもできます。
  
これらの各タスクを実行するための詳細ステップについては、このセクションの手順を参照してください。
  
## <a name="in-this-section"></a>このセクションの内容

- [音声ポリシーを作成または変更し、Skype for Business で PSTN 使用法レコードを構成する](voice-policy-and-pstn-usage-records.md)
    
- [Skype for Business でボイス メール エスケープを構成する](configure-voice-mail-escape.md)
    
- [Skype for Business での PSTN 使用法レコードの表示](view-pstn-usage-records.md)
    
- [Skype for Business でボイス ルートを作成または変更する](create-or-modify-a-voice-route.md)
    
- [Skype for Business でボイス ルート構成ファイルをエクスポートまたはインポートする](voice-route-configuration-import-export.md)
    
- [Skype for Business での音声ルーティング構成に対する保留中の変更の公開](voice-route-config-changes.md)
    

