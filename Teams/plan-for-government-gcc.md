---
title: マイクロソフト チームが Microsoft 365 政府の GCC の展開の計画します。
author: lolajacobsen
ms.author: lehewe
manager: serdars
ms.date: 07/26/2018
ms.topic: article
ms.service: msteams
ms.reviewer: lehewe
description: 米国政府の規制の対象となるデータを処理するエンティティでドライブ Office 365 の展開を IT プロフェッショナルのためのガイダンス
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 430b6c6de5468442f7a290b07b28eb59d276e00c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885773"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Microsoft 365 政府の GCC の展開の計画

このガイダンスは米国連邦政府、状態、航空写真や民族のお、ローカル政府機関や政府の規制や要件の対象となるデータを処理する他のエンティティで、Office 365 の導入を促進する IT プロフェッショナルには、Microsoft の使用365 政府の GCC は、これらの要件を満たすために適しています。

> [!NOTE]
> 組織が既に Microsoft 365 政府の GCC の適格性の要件が満たされるとに適用され、プログラムに受け入れられた、1 ~ 4 の手順をスキップして、展開を開始するのには 5 の手順に進みます。 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>手順 1 です。 組織が Microsoft 365 政府の GCC を必要があるし、適格性の要件を満たしているかどうかを決定します。 

Microsoft 365 政府の GCC 環境を提供米国への準拠 FedRAMP 中、刑事裁判および連邦の税情報システム (CJI と FTI のデータ型) の要件など、クラウド サービスの政府の要件。

Office 365 の機能を楽しむだけでなくは、組織はマイクロソフト 365 政府の GCC に固有の以下の機能を活用できます。

-   組織の顧客のコンテンツが Microsoft の商用の Office 365 サービスでお客様のコンテンツ論理的に分離します。
-   組織の顧客のコンテンツは、米国内に格納されます。
-   組織の顧客のコンテンツへのアクセスは、スクリーンの Microsoft の担当者に限定されます。
-   Microsoft 365 政府の GCC は、証明書および米国の公的機関のお客様に必要な認定に準拠します。

Microsoft 365 政府 - 米国政府の[Office 365 の政府の計画](https://products.office.com/government/compare-office-365-government-plans)などの[特典を受ける](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)お客様は、提供する GCC の詳細についてを見つけることができます。

[Office 365 の米国政府のサービスの説明](https://technet.microsoft.com/library/mt774581.aspx)では、プラットフォームの利点は、米国内でのコンプライアンス要件を満たすことの中心は、について説明します。

> [!Tip]
> サービスの説明内の情報のテーブルを Excel ブックに転送し、2 つの列を追加することができます:**はい/いいえ、組織内での関連性**と**Y か N は、自分の組織のニーズに対応**します。 このサービスが組織のニーズを満たしていることを確認するのには、同僚と、この一覧を確認できます。


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>意思決定ポイント|<ul><li>Microsoft 365 政府の GCC は、組織の適切なかどうかを決定します。</li><li>組織が適格性の要件を満たしていることを確認します。</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>Microsoft 365 政府の GCC が提供する機能を理解します。</li></ul>|

> [!Note]
> Microsoft 365 政府の GCC をアメリカ合衆国ではできるだけです。 -米国以外の政府機関のお客様は、いくつかの[Office 365 の政府の計画](https://products.office.com/en/government/compare-office-365-government-plans)から選択できます。

## <a name="step-2-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>手順 2 です。 機能は、現在利用できないか、既定で無効になっているを理解します。 

Microsoft 365 政府の GCC をいくつかの相違がある、政府のクラウドのお客様の要件に合わせて、およびエンタープライズのプランです。 次の表に記載されている機能はご利用いただけません。

| 機能                     | 理由            |
|-----------------------------|-------------------|
| 通話とミーティングのレコーディング  | 記録はマイクロソフトのストリームは、将来的に米国政府の計画で使用可能になります。 |
| アプリ       | アプリケーション (コンポーネント、タブ、コネクタなど) は使用できません、最初に、利用できるように、すべてのコンポーネントは、FedRAMP 中コンプライアンス基準を満たしてとすぐに取り組んでいます。 |
| チャネルを電子メールで送信します。             | 政府の計画では、現在のアーキテクチャの機能はサポートされていません。 |
| プレゼンスの統合            | 私たちはこの重要な機能の最初の企業のお客様のための仕上げの作業です。 政府の顧客に利用可能な将来的にします。 |
| チームとデバイス間の相互運用機能のチャット ユーザー            | 相互運用機能は、統合プレゼンス サービス (UPS) に依存して、UPS の GCC のチームのテナントを有効にするまで使用できません。 |

|通知を電子メールで送信。米国政府の計画では、現在のアーキテクチャの機能はサポートされていません。 作業は、この機能が使用できるように米国政府の計画の顧客、将来的に継続的です。 |


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Microsoft 365 政府の GCC の機能セットが、組織のニーズを満たしているかどうかを決定します。</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>既定のセキュリティ設定を理解します。</li></ul>|

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>ステップ 3 です。 Microsoft 365 政府の GCC のデフォルトのセキュリティ設定を理解します。

[管理とセキュリティの設定](enable-features-office-365.md)を見直し、それらを変更し、既定のセキュリティ設定を変更する前に、コンプライアンスへの影響を検討する前に時間がかかることをお勧めします。

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Microsoft 365 政府の GCC のセキュリティ設定を既定値のいずれかを変更するかどうかの変更の影響を理解して最初に解決する可能性がありますを行うかを決定します。</li></ul> |

## <a name="step-4-apply-for-microsoft-365-government---gcc"></a>手順 4 します。 Microsoft 365 政府の GCC を適用します。

持つことに、このサービスがお客様の組織は、[このサービスは、ここに適用する](https://products.office.com/government/eligibility-validation)プロセスを開始します。

## <a name="step-5-plan-for-governance"></a>手順 5 です。 ガバナンスの計画

コーポレート ・ ガバナンスとどのように満たすことがお客様の要件を決定します。 詳細については、[チームの管理のための計画](plan-teams-governance.md)に移動します。

## <a name="step-6-deploy-teams-for-collaboration"></a>手順 6。 チームの共同作業を展開します。

Microsoft 365 政府の GCC では、onboarded をした後[FastTrack](https://fasttrack.microsoft.com/fasttrack-faq)と、選択したパートナー サービスにオンボードを使用する標準的な展開方法に従います。

準備ができたら、[チーム、およびチャネルを通じて、組織内でのコラボレーションを有効に](teams-overview.md)するチームを展開します。 採用し、変更管理のチームまたはチームのエキスパートと協力することを確認します。

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>手順 7 です。 会議および音声のチームを配置します。

広く利害関係者グループにチームを使用して、会議や[クラウドのボイス機能](cloud-voice-deployment.md)を展開するための計画を開始する絶好の機会です。

