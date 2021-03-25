---
title: Microsoft 365 Government - GCC の展開
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 米国政府規制の対象となるデータを処理するエンティティでの Microsoft 365 展開を支援する IT プロ向けガイダンス
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ecc733c181e268dd6092f169e91d2f9acb4ee47
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117835"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Microsoft 365 Government の計画 - GCC 展開

このガイダンスは、MICROSOFT 365 Government - GCC の使用がこれらの要件を満たすために適切である、政府の規制と要件の対象となるデータを扱う米国連邦、州、地域、部下、または地域の政府エンティティ、または他のエンティティで Microsoft 365 の展開を推進している IT のプロを対象とします。 新しい 2020 年 3 月 26 日: GCC のダウンロード [可能なクイック スタート ガイドをお見逃しなく](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)。

> [!IMPORTANT]
> Microsoft Teams では、コロンウイルス (COVID-19) パンデミックが原因で、オンライン通話や音声/ビデオ会議が急増しています。<br/>
> 
>マイクロソフトでは、通話の前例のない増加に対応し、継続性と可用性を確保するために、Microsoft Teams GCC オーディオ/ビデオ サーバーが業務用データセンターや政府機関のデータセンターの処理能力を活用できるようにしています。<br/>
> 
>これらのオーディオ/ビデオ サーバーは、米国の Microsoft Azure FedRAMP High の認可境界サーバー内に存在し、顧客のコンテンツを格納しません。 ただし、これらのサーバーは通話や会議の音声とビデオを処理し、この中間期間中は業務スタッフの下で動作しています。<br/>
> 
>有資格の審査担当者は、これらのサーバーへの対話型のログオンを確認することで、顧客データへのアクセスの可能性について、これらのサーバーを監視しています。 資格のある担当者は、顧客コンテンツへのアクセスに関する GCC 要件を満たしています。 審査要件の詳細については、GCC サービスの説明 [を参照してください](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)。<br/>
> 
>このたびは、弊社のサービスが利用可能で信頼性の高い状態を維持するための手順を取り入れていますので、サポートに感謝します。<br/>


> [!NOTE]
> 組織が Microsoft 365 Government - GCC の利用資格要件を既に満たし、プログラムに適用され、プログラムに同意されている場合は、手順 1 と 2 をスキップして、手順 3 に直接進みます。 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>手順 1. 組織が Microsoft 365 Government - GCC を必要とするかどうかを決定し、資格要件を満たしています。 

Microsoft 365 Government - GCC 環境は、FedRAMP Moderate などのクラウド サービスに関する米国政府の要件、および犯罪犯罪および連邦税情報システム (CJI および FTI データの種類) の要件を遵守します。

組織は、Microsoft 365 の機能を利用できるだけでなく、Microsoft 365 Government - GCC 固有の次の機能を利用できます。

-   組織の顧客コンテンツは、商用の Microsoft 365 サービスの顧客コンテンツから Microsoft から論理的に分離されます。
-   組織の顧客コンテンツは米国内に保存されます。
-   組織の顧客コンテンツへのアクセスは、Microsoft の担当者に限定されます。
-   Microsoft 365 Government - GCC は、米国の公共機関のお客様に必要な認定と認定に準拠しています。

米国政府機関向け Microsoft 365 Government - GCC サービスの詳細については [、Microsoft 365 Government](https://products.office.com/government/compare-office-365-government-plans)プラン (資格要件を含む) [をご覧ください](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)。

[Microsoft 365 US Government](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)サービスの説明では、プラットフォームの利点について説明します。これは、米国内のコンプライアンス要件を満たしていることを中心にしています。

> [!Tip]
> サービスの説明の情報テーブルを Excel ブックに転送し、組織 **の Y/N** に関連し、組織の **Y/N** のニーズを満たすという 2 つの列を追加することができます。 その後、このリストを同僚と確認して、このサービスが組織のニーズを満たしたと確認できます。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Microsoft 365 Government - GCC が組織に適したかどうかを決定します。</li><li>組織が資格要件を満たしていることを確認します。</li></ul> |

> [!Note]
> Microsoft 365 Government - GCC は米国でのみご利用いただけます。 米国政府機関以外のお客様は [、Microsoft 365 Government プランから選択できます](https://products.office.com/en/government/compare-office-365-government-plans)。


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>手順 2. Microsoft 365 Government - GCC に申し込む

このサービスが組織に合っている場合は、ここでこのサービスを申請する [プロセスを開始します](https://products.office.com/government/eligibility-validation)。

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>手順 3. Microsoft 365 Government - GCC の既定のセキュリティ設定について説明します。

管理者とセキュリティ設定を変更する前に慎重[](enable-features-office-365.md)に確認し、既定のセキュリティ設定を変更する前にコンプライアンスへの影響を考慮することをお勧めします。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Microsoft 365 Government - GCC の既定のセキュリティ設定を変更するかどうかを決定し、最初に変更の影響を理解します。</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>手順 4. 既定で現在使用できない機能または無効になっている機能を理解します。

政府機関向けクラウドのお客様の要件に対応するために、Microsoft 365 Government - GCC プランと Enterprise プランにはいくつかの違いがあります。 使用できる機能を確認するには、次の表を参照してください。

[Microsoft Teams サービスの説明](/office365/servicedescriptions/teams-service-description)

> [!Note]
> GCC クラウドで他のワークロードを完全に利用できると、すべての追加統合作業が完了すると、そのワークロードは Teams で利用できます。


|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Teams 機能セットが組織のニーズを満たすかどうかを決定します。</li></ul> |

## <a name="step-5-plan-for-governance"></a>手順 5. ガバナンスの計画

ガバナンスの要件とそれらを満たす方法を決定します。 詳細については [、「Teams のガバナンスの計画」](plan-teams-governance.md) を参照してください。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Teams のガバナンス計画のガイドラインに従って、ガバナンス要件を [決定して文書化します](plan-teams-governance.md)。</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>手順 6. 共同作業のために Teams を展開する

Microsoft 365 Government – GCC にオンボードされた後は、「Microsoft Teams を展開する方法」で説明されている推奨される展開パス [に従います](./deploy-overview.md)。 導入および変更管理チームと Teams のチャンピオンと必ず関与してください。

また、FastTrack または選択 [したパートナー](https://www.microsoft.com/fasttrack) と一緒にサービスをオンボードできます。

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>手順 7. 会議と音声用の Teams を展開する

また、Teams を幅広い関係者グループと一緒に使用して、会議やクラウド音声機能の展開計画を開始する最適な [時間です](./cloud-voice-landing-page.md)。