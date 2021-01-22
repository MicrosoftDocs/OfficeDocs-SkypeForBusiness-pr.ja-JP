---
title: Teams の音声 Contoso のケース スタディ
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 多国籍企業向け Teams 音声ケース スタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6ee08fa7bdeb1ded6bda384115a08048021cb67
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918733"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Contoso のケース スタディ: 自動応答と通話キュー

Contoso は、オンプレミスの Skype for Business 展開からの自動応答と通話キューに慣れ親しんでいます。 クラウド自動応答と通話キューを設定する方法を理解するために、Teams の自動応答と通話キューのプラン [を確認しました](plan-auto-attendant-call-queue.md)。

## <a name="requirements-depending-on-site-type"></a>サイトの種類に応じて要件

サイトの種類に応じて、Contoso には次のニーズがありました。

- サイトの種類 A: 従来のレガシ テレフォニー システム 

  受付係と同じ電話番号を自動応答の番号と関連付けるのに必要なサイトタイプ A。 これらの各サイトの主要な部門には、チーム メンバーにルーティングされる独自の通話キューがあります。 直接ルーティングを使用した電話システムと通話プラン付き電話システムを使用するサイトが混同されています。  

- サイトの種類 B: Skype for Business エンタープライズ VoIP 

  サイトの種類 B には、Teams への移行に必要な既存の自動応答と通話キューがありました。 Contoso は、自動応答に関連付けられている電話番号を保持する必要がありました。 Contoso は、これらのサイトの大部分を通話プランを使用する電話システムに移行しました。 ただし、通話プランを利用できないいくつかの場所で、Contoso はこれらのサイトを直接ルーティング構成に移動しました。  

- サイトの種類 C: Skype for Business エンタープライズ VoIP &従来のテレフォニー システム 

  サイトの種類 C には、従来のレガシ テレフォニー システムに存在する既存の自動応答がありました。 このサイトの決定と構成は、サイトの種類 A と同じでした。   

- すべてのサイトの種類について、Contoso は次の質問をしました。

  - Q: 新しい数値または既存の数値を使用しますか? 
    A: Contoso は、自動応答のサービス アカウントに割り当てる既存の電話番号を使用することを決定しました。 

  - Q: 着信通話を受け取る自動応答は、いつ利用できますか? 
    A: Contoso は営業時間を設定し、営業時間が "営業時間外" の自動応答にリダイレクトされた後に着信を受信しました。  

  - Q: 通話キュー内のメンバー (アテンダント、シリアル、ラウンド ロビン ルーティング) に通話をルーティングする方法 
    A: Contoso はアテンダント ルーティングを使用することを決定しました。 

  - Q: ユーザーがいついつ通話を受けるべきか、それとも受けるべきでないのかを判断するにはどうすればいいでしょうか。 
    A: Contoso は、エージェントが利用可能かどうかを判断するために通話処理オプションを使用することを決定しました。プレゼンス ベースのルーティング。 


## <a name="configuration"></a>構成

自動応答と通話キューを設定する手順については、「リソース アカウントを管理する」で説明されている [次の手順が含まれます](manage-resource-accounts.md)。 

1. サービス番号を取得します。 

2. 無料の電話システム - 仮想ユーザー ライセンスまたは有料電話システム ライセンスを取得して、リソース アカウントまたは電話システム ライセンスで使用します。

3. リソース アカウントを作成します。 自動応答または通話キューは、関連付けられたリソース アカウントを持っている必要があります。 

4. 電話システムまたは電話システム - 仮想ユーザー ライセンスをリソース アカウントに割り当てる。 詳細については [、「Microsoft 365 電話システム - 仮想ユーザー ライセンス」を参照してください](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user)。

5. ライセンスを割り当てたリソース アカウントにサービス電話番号を割り当てる。 

6. 電話システム通話キューまたは自動応答を作成する 

7. リソース アカウントを通話キューまたは自動応答にリンクします。 


### <a name="sites-with-phone-system-with-direct-routing"></a>直接ルーティングが設定された電話システムを使用するサイト 

Contoso は、365 年 365 日にローカルの通信事業者から提供された電話番号をサービス番号としてOffice必要でした。 

- Contoso は、直接ルーティングで利用できる電話番号を設定するために、「リソース アカウントの管理」の手順 [に従いました](manage-resource-accounts.md)。 365 Officeオンプレミスの電話番号を認識していないので、Contoso は PowerShell を使用してセットアップを完了しました。   

- クラウド自動応答を構成するには、「クラウド自動応答を設定する」で説明されている手順 [に従います](create-a-phone-system-auto-attendant.md)。 

- クラウド通話キューを設定するには、「クラウド通話キューを作成する」で説明されている手順 [に従います](create-a-phone-system-call-queue.md)。  


### <a name="sites-with-phone-system-with-calling-plan"></a>通話プランが設定された電話システムを使用するサイト

Contoso は、Skype for Business の自動応答に使用された電話番号を 365 エンタープライズ VoIP 365 電話システムOffice移行する必要があります。 これにより、自動応答として使用するサービス番号として同じ番号を割り当てる必要がありました。 

- 電話番号を移行するために、Contoso は [「電話番号](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) を Teams に移行する」の手順に従い、組織の電話番号の管理に関する追加のガイダンス [を取得しました](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)。

- クラウド自動応答を構成するには、「クラウド自動応答を設定する」で説明されている手順 [に従います](create-a-phone-system-auto-attendant.md)。

-  クラウド通話キューを設定するには、「クラウド通話キューを作成する」で説明されている手順 [に従います](create-a-phone-system-call-queue.md)。  

 