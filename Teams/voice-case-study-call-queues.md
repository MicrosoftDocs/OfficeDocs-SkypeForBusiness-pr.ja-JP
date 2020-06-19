---
title: チームボイスの Contoso のケーススタディ
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
description: 多国籍企業向けの Teams の音声のケーススタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: 780d812b4e6e56b28b867ace14dbf1d5f6170302
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786093"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Contoso のケーススタディ: 自動応答と通話キュー

Contoso は、オンプレミスの Skype for Business 展開の自動応答と通話キューに精通していました。 クラウド自動応答のセットアップ方法を理解するために、[クラウド自動応答の](what-are-phone-system-auto-attendants.md)概要と[小規模ビジネスの例-自動応答のセットアップ](tutorial-org-aa.yml)に関するチュートリアルをご覧ください。 通話キューのセットアップに使用できるオプションの詳細については、[Contoso レビュー][クラウドの通話キューを作成](create-a-phone-system-call-queue.md)します。  

## <a name="requirements-depending-on-site-type"></a>サイトの種類に応じた要件

Contoso には、サイトの種類に応じて次の要件があります。

- サイトの種類 A: 従来の従来のテレフォニーシステム 

  [サイトの種類の場合、受付に関連付けられた電話番号を自動応答の番号として保持する必要があります。 各サイトの主要部署には、チームメンバーにルーティングされる専用の通話キューがあります。 通話プランを使って、直通ルーティングと電話システムで電話システムを使用しているサイトが混在していました。  

- サイトの種類 B: Skype for Business のエンタープライズボイス 

  サイトの種類 B には、チームへの移行に必要な既存の自動応答と通話キューがありました。 Contoso は、電話番号を自動応答に関連付けておく必要があります。 Contoso がこれらのサイトの大部分を電話システムに移行しました。 ただし、通話プランを利用できない場所では、Contoso がこれらのサイトを直接ルーティング構成に移行しました。  

- サイトの種類 C: Skype for Business エンタープライズボイス & 従来の従来のテレフォニーシステム 

  サイトの種類 C には、従来の従来のテレフォニーシステムに含まれていた既存の自動応答がありました。 このサイトの決定と構成は、サイトの種類 A と同じです。   

- すべてのサイトの種類について、Contoso から以下の質問が寄せられています。

  - Q: 新規または既存の番号を使用しますか? 
    A: Contoso は、自動応答のサービスアカウントに割り当てられる既存の電話番号を使用することを決定しました。 

  - Q: 自動応答はどのようなタイミングで着信を受け入れることができますか? 
    A: Contoso は、勤務時間を設定することを決定し、営業時間が "勤務時間" の自動応答にリダイレクトされた後で通話を受信することにしました。  

  - Q: 通話キュー内のメンバーへの通話は、アテンダント、シリアル、またはラウンドロビンルーティングのどのようにルーティングされますか? 
    A: Contoso は、アテンダントルーティングを使用することを決定しました。 

  - Q: ユーザーが通話を受けるべきかどうかを判断する方法を教えてください。 
    A: Contoso は、エージェントが利用可能かどうかを判断するために、通話処理オプションの使用を決定しました。プレゼンスベースのルーティング。 


## <a name="configuration"></a>構成

自動応答と通話キューを設定する手順については、「[リソースアカウントを管理](manage-resource-accounts.md)する」に記載されています。 

1. サービス番号を取得します。 

2. リソースアカウントまたは電話システムのライセンスと共に使用する、無料の電話システム仮想ユーザーライセンスまたは有料電話システムライセンスを取得します。

3. リソースアカウントを作成します。 関連付けられているリソースアカウントを持つには、自動応答または通話キューが必要です。 

4. 電話システムまたは電話システム仮想ユーザーライセンスをリソースアカウントに割り当てます。 詳細については、「 [Microsoft 365 電話システム–仮想ユーザーライセンス](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user)」を参照してください。

5. ライセンスを割り当てたリソースアカウントにサービスの電話番号を割り当てます。 

6. 電話システムの通話キューまたは自動応答を作成する 

7. リソースアカウントを通話キューまたは自動応答にリンクします。 


### <a name="sites-with-phone-system-with-direct-routing"></a>直接ルーティングを使用する電話システムを使用しているサイト 

Contoso は、Office 365 のサービス番号として、ローカルの通信事業者から提供される電話番号を設定する必要がありました。 

- 直接ルーティングによって利用可能な電話番号を設定するには、「[リソースアカウントの管理](manage-resource-accounts.md)」に記載された手順に従います。 Office 365 はオンプレミスの電話番号を認識しないため、Contoso は PowerShell を使用してセットアップを完了します。   

- クラウド自動応答を構成するには、「[クラウド自動応答を設定](create-a-phone-system-auto-attendant.md)する」の手順に従ってください。 

- クラウド通話キューをセットアップするには、「[クラウド通話キューを作成](create-a-phone-system-call-queue.md)する」で説明した手順に従います。  


### <a name="sites-with-phone-system-with-calling-plan"></a>通話プランのある電話システムを使用するサイト

Contoso は、Skype for Business のエンタープライズボイス自動応答に使用された電話番号を、Office 365 電話システムに移植する必要がありました。 これにより、自動応答として使用するために、同じ番号をサービス番号として割り当てることができます。 

- 電話番号を移植するには、「会社[に電話番号を移行](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)する」の指示に従って、「[組織の電話番号を管理](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)する」で追加のガイダンスを入手します。

- クラウド自動応答を構成するには、「[クラウド自動応答を設定](create-a-phone-system-auto-attendant.md)する」の手順に従ってください。

-  クラウド通話キューをセットアップするには、「[クラウド通話キューを作成](create-a-phone-system-call-queue.md)する」で説明した手順に従います。  

 