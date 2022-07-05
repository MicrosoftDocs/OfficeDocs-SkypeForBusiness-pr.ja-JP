---
title: 'Teams 音声 Contoso のケース スタディ: 自動応答と通話キュー'
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
description: '多国籍企業向けの Teams 音声ケース スタディ: 自動応答と通話キュー'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50d1ee2d384b200aeab6eefd6ca2de623015b6f2
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615843"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Contoso のケース スタディ: 自動応答と呼び出しキュー

Contoso は、オンプレミスのSkype for Businessデプロイからの自動応答と呼び出しキューに精通していました。 クラウド自動応答と通話キューを設定する方法を理解するために、 [Teams の自動応答と通話キューの計画](plan-auto-attendant-call-queue.md)を確認しました。

## <a name="requirements-depending-on-site-type"></a>サイトの種類に応じた要件

サイトの種類に応じて、Contoso には次のニーズがありました。

- サイトタイプ A: 従来のレガシ テレフォニー システム 

  自動応答の番号と同じ電話番号を受付担当者に関連付けるために必要なサイト タイプ A。 これらの各サイトの主要部門には、チーム メンバーにルーティングする独自の通話キューがあります。 通話プランと直接ルーティングと電話システムで電話システムを使用するサイトが混在していました。  

- サイトの種類 B: Skype for Business エンタープライズ VoIP 

  サイト タイプ B には、Teams への移行に必要な既存の自動応答と通話キューがありました。 Contoso は、自動応答に関連付けられている電話番号を保持する必要があります。 Contoso は、これらのサイトの大部分を通話プランを使用して電話システムに移行しました。 ただし、通話プランを使用できなかったいくつかの場所で、Contoso はこれらのサイトをダイレクト ルーティング構成に移動しました。  

- サイトタイプ C: 従来のテレフォニー システムSkype for Business エンタープライズ VoIP & 

  サイト タイプ C には、従来のレガシ テレフォニー システムに存在する既存の自動応答がありました。 このサイトの決定と構成は、サイトタイプ A と同じでした。   

- すべてのサイトの種類について、Contoso は次の質問をしました。

  - Q: 新しい番号または既存の番号を使用しますか? 
    A: Contoso は、既存の電話番号を使用して、自動応答のサービス アカウントに割り当てることにしました。 

  - Q: 自動応答で着信呼び出しを受け入れるのはいつですか? 
    A: Contoso は営業時間を設定し、営業時間後に着信した通話を "時間外" 自動応答にリダイレクトすることにしました。  

  - Q: 通話は、通話キュー内のメンバー (アテンダント、シリアル、ラウンド ロビン ルーティング) にどのようにルーティングされますか。 
    A: Contoso は、アテンダント ルーティングを使用することにしました。 

  - Q: ユーザーがいつ呼び出しを受ける必要があるか、呼び出すべきでないかを判断するにはどうすればよいですか? 
    A: Contoso は、呼び出し処理オプションを使用して、エージェントが使用可能かどうかを判断することにしました。プレゼンス ベースのルーティングです。 

## <a name="configuration"></a>構成

自動応答と呼び出しキューを設定する手順については、 [リソース アカウントの管理](manage-resource-accounts.md)に関するページで説明されています。

1. サービス番号を取得します。

2. リソース アカウントまたは電話システム ライセンスで使用する無料 **のMicrosoft Teams 電話 リソース アカウント** ライセンスまたは有料の電話システム ライセンスを取得します。

3. リソース アカウントを作成します。 自動応答または呼び出しキューは、関連付けられたリソース アカウントを持っている必要があります。

4. **Teams 電話スタンダード** または **Microsoft Teams 電話リソース アカウント** のライセンスをリソース アカウントに割り当てます。 詳細については、「[リソース アカウント ライセンスMicrosoft Teams 電話](./teams-add-on-licensing/virtual-user.md)」を参照してください。

5. ライセンスを割り当てたリソース アカウントにサービス電話番号を割り当てます。

6. 電話システム通話キューまたは自動応答を作成します。

7. リソース アカウントを通話キューまたは自動応答にリンクします。

### <a name="sites-with-phone-system-with-direct-routing"></a>直接ルーティングを使用する電話システムを使用するサイト

Contoso は、Office 365のサービス番号として、ローカルキャリアから提供される電話番号を設定する必要がありました。

- 直接ルーティングで使用できる電話番号を設定するために、Contoso は [リソース アカウントの管理](manage-resource-accounts.md)に関するページの指示に従いました。 Office 365はオンプレミスの電話番号を認識していないため、Contoso は PowerShell を使用してセットアップを完了しました。   

- クラウド自動応答を構成するために、Contoso はクラウド自動応答のセットアップに関するページで説明されている手順 [に](create-a-phone-system-auto-attendant.md)従いました。 

- クラウド呼び出しキューを設定するために、Contoso はクラウド呼び出し [キューの作成](create-a-phone-system-call-queue.md)に関する記事に記載されている手順に従いました。  


### <a name="sites-with-phone-system-with-calling-plan"></a>通話プランがある電話システムを持つサイト

Contoso は、Office 365 電話システムに自動応答をSkype for Business エンタープライズ VoIPするために使用された電話番号を移植する必要がありました。 これにより、自動応答として使用するサービス番号と同じ番号を割り当てることができました。 

- 電話番号を移植するために、Contoso は [Teams に電話番号を転送する](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) の手順に従い、 [組織の電話番号の管理に関](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する追加のガイダンスを取得しました。

- クラウド自動応答を構成するために、Contoso はクラウド [自動応答のセットアップ](create-a-phone-system-auto-attendant.md)に関するページで説明されている手順に従いました。

-  クラウド呼び出しキューを設定するために、Contoso はクラウド呼び出し [キューの作成](create-a-phone-system-call-queue.md)に関する記事に記載されている手順に従いました。  

