---
title: Teams Contoso のケース スタディ
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
description: Teams企業向け音声ケース スタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0cb8029a8f4e979a76afe069ee9b22e7be897913
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121295"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Contoso のケース スタディ: 自動応答と通話キュー

Contoso は、オンプレミスのサービスのデプロイから自動応答と通話キューをSkype for Businessでした。 クラウド自動応答と通話キューを設定する方法を理解するために、「自動応答と通話キューの計画Teams」[を確認しました](plan-auto-attendant-call-queue.md)。

## <a name="requirements-depending-on-site-type"></a>サイトの種類に応じて要件

サイトの種類に応じて、Contoso には次のニーズがありました。

- サイトの種類 A: 従来のレガシ テレフォニー システム 

  サイトの種類 A は、受付に関連付けられている電話番号を、自動応答の番号と同じに維持するために必要です。 これらの各サイトの主要な部門には、チーム メンバーにルーティングされる独自の呼び出しキューがあります。 直接ルーティングと呼び出しプランで電話システムサイトが電話システムいました。  

- サイトの種類 B: Skype for Business エンタープライズ VoIP 

  サイトタイプ B には、既存の自動応答と通話キューが含み、このキューをサイトに移行する必要Teams。 Contoso は、自動応答に関連付けられている電話番号を保持する必要がありました。 Contoso は、これらのサイトの大部分を通話プラン電話システムに移動しました。 ただし、通話プランを利用できないいくつかの場所で、Contoso はこれらのサイトを直接ルーティング構成に移動しました。  

- サイトの種類 C: Skype for Business エンタープライズ VoIP &レガシ テレフォニー システム 

  サイト タイプ C には、従来のレガシ テレフォニー システムに存在する既存の自動応答がありました。 このサイトの決定と構成は、サイトタイプ A と同じでした。   

- すべてのサイトの種類について、Contoso は次の質問をしました。

  - Q: 新規または既存の数値を使用しますか。 
    A: Contoso は、自動応答のサービス アカウントに割り当てる既存の電話番号を使用することを決定しました。 

  - Q: 着信通話を受け入れる自動応答を利用できるのは、いつですか。 
    A: Contoso は営業時間を設定し、営業時間後に "時間外" 自動応答にリダイレクトされた通話を受信しました。  

  - Q: 呼び出しは、応答、シリアル、ラウンド ロビン ルーティングの呼び出しキュー内のメンバーにルーティングされますか。 
    A: Contoso は、アテンダント ルーティングを使用することを決定しました。 

  - Q: ユーザーが通話を受け取る必要があるかどうかは、どのように判断しますか。 
    A: Contoso は、通話処理オプションを使用して、エージェントが使用可能かどうかを判断することを決定しました。プレゼンス ベースのルーティングです。 


## <a name="configuration"></a>構成

自動応答と通話キューを設定する手順については、リソース アカウントの管理に関するページ [で説明されています](manage-resource-accounts.md)。 

1. サービス番号を取得します。 

2. 無料の電話システム - 仮想ユーザー ライセンスまたは有料の 電話システム ライセンスを取得して、リソース アカウントまたはリソース ライセンスで使用電話システムします。

3. リソース アカウントを作成します。 自動応答または通話キューは、関連付けられているリソース アカウントを持っている必要があります。 

4. リソース アカウント電話システムまたは仮想電話システム - 仮想ユーザー ライセンスを割り当てる。 詳細については、「仮想ユーザー ライセンス[Microsoft 365 電話システム 」 を参照してください](./teams-add-on-licensing/virtual-user.md)。

5. ライセンスを割り当てたリソース アカウントにサービス電話番号を割り当てる。 

6. 通話キュー電話システム自動応答を作成する 

7. リソース アカウントを通話キューまたは自動応答にリンクします。 


### <a name="sites-with-phone-system-with-direct-routing"></a>直接ルーティングを電話システムサイト 

Contoso は、ローカル通信会社から提供された電話番号を、サービス番号として設定する必要Office 365。 

- 直接ルーティングで利用できる電話番号を設定するために、Contoso は「リソース アカウントの管理」にある手順 [に従いました](manage-resource-accounts.md)。 オンプレミスOffice 365を認識していないので、Contoso は PowerShell を使用してセットアップを完了しました。   

- クラウド自動応答を構成するために、Contoso は「クラウド自動応答を設定する」で説明 [されている手順に従いました](create-a-phone-system-auto-attendant.md)。 

- クラウド通話キューを設定するために、Contoso は「クラウド通話キューを作成する」で説明 [されている手順に従いました](create-a-phone-system-call-queue.md)。  


### <a name="sites-with-phone-system-with-calling-plan"></a>通話プラン電話システムサイト

Contoso は、自動応答に使用された電話番号をSkype for Business エンタープライズ VoIPに移行Office 365 電話システム。 これにより、自動応答として使用するサービス番号として同じ番号を割り当てることができます。 

- Contoso は、電話番号を移行するために、「電話番号を Teams[](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)に転送する」の手順に従い、「組織の電話番号を管理する」で追加のガイダンス[を取得しました](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

- クラウド自動応答を構成するために、Contoso は「クラウド自動応答を設定する」で [説明されている手順に従いました](create-a-phone-system-auto-attendant.md)。

-  クラウド通話キューを設定するために、Contoso は「クラウド通話キューを作成する」で説明 [されている手順に従いました](create-a-phone-system-call-queue.md)。  

