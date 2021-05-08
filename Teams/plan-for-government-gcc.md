---
title: Microsoft 365Government - GCC デプロイ
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: IT のプロが、米国政府規制Microsoft 365データを処理するエンティティでのデプロイを支援するガイダンス
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
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Microsoft 365 Government の計画 - GCCデプロイ

このガイダンスは、Microsoft 365 Government - GCC の使用がこれらの要件を満たすために適切である、政府の規制と要件の対象となるデータを処理する米国連邦政府、州、地方、部族、または地域政府のエンティティ、または他のエンティティへの Microsoft 365 の展開を推進している IT プロを対象とします。 新しい 2020 年 3 月 26 日: ダウンロード可能なクイック スタート ガイドをお見逃[GCC。](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)

> [!IMPORTANT]
> Microsoft Teamsウイルス (COVID-19) パンデミックにより、オンライン通話や音声/ビデオ会議が急増しています。<br/>
> 
>これまでにない呼び出しの増加に対応し、継続性と可用性を確保するために、Microsoft は、Microsoft Teams GCC オーディオ/ビデオ サーバーが商用データセンターと政府機関のデータセンターの処理能力を活用できるようにしています。<br/>
> 
>これらのオーディオ/ビデオ サーバーは、米国の Microsoft Azure FedRAMP High 認定境界サーバー内に存在し、顧客コンテンツを格納しません。 ただし、これらのサーバーは通話や会議の音声とビデオを処理し、この中間期間中は業務スタッフの下で動作しています。<br/>
> 
>有資格の審査担当者は、これらのサーバーへの対話型ログオンを確認することで、顧客データへの潜在的なアクセスをこれらのサーバーで監視しています。 資格のある担当者は、GCCコンテンツにアクセスするために必要な要件を満たします。 スクリーニング要件の詳細については、「サービスの説明[」GCC参照してください](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)。<br/>
> 
>これらの特別な時間にサービスを確実に利用し、信頼性を維持するための手順を実行して、サポートに感謝します。<br/>


> [!NOTE]
> 組織が既に Microsoft 365 Government - GCC の資格要件を満たし、プログラムに適用され、プログラムに同意されている場合は、手順 1 と 2 をスキップして、手順 3 に直接進みます。 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>手順 1. 組織が Government を使用する必要Microsoft 365、GCC要件を満たしていることを確認します。 

Microsoft 365 Government - GCC 環境は、FedRAMP Moderate などのクラウド サービスに関する米国政府の要件、および刑事判事および連邦税情報システム (CJI および FTI データ型) の要件に準拠しています。

組織は、Microsoft 365 の機能を利用できるだけでなく、Microsoft 365 Government - GCC に固有の機能を利用できます。

-   組織の顧客コンテンツは、Microsoft の商用サービスの顧客コンテンツMicrosoft 365分離されます。
-   組織の顧客コンテンツは米国内に保存されます。
-   組織の顧客コンテンツへのアクセスは、Microsoft の担当者に限定されます。
-   Microsoft 365Government - GCC、米国の公的機関のお客様に必要な認定と認定に準拠しています。

米国政府のお客様向け Microsoft 365 Government - GCC オファリングの詳細については[、Microsoft 365 Government](https://products.office.com/government/compare-office-365-government-plans)プランに関するページを参照してください。資格要件を[含む](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements))。

米国[政府Microsoft 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)の説明では、米国内のコンプライアンス要件を満たしていることを中心にしたプラットフォームの利点について説明します。

> [!Tip]
> サービスの説明の情報のテーブルを Excel ブックに転送し、2 つの列を追加することができます。組織 **の Y/N** に関連し、組織の **Y/N** のニーズを満たします。 その後、この一覧を同僚と確認して、このサービスが組織のニーズを満たしたと確認できます。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>組織に適Microsoft 365 Government - GCCを決定します。</li><li>組織が資格要件を満たしていることを確認します。</li></ul> |

> [!Note]
> Microsoft 365Government - GCCは米国でのみ使用できます。 米国政府以外のお客様は、複数の政府機関向[けプランMicrosoft 365選択できます](https://products.office.com/en/government/compare-office-365-government-plans)。


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>手順 2. Microsoft 365 Government - GCC に申し込む

このサービスが組織に正しいと決定した後、このサービスに適用するプロセスをここから [開始します](https://products.office.com/government/eligibility-validation)。

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>手順 3. Government のMicrosoft 365 - 既定GCC設定について説明します。

管理者とセキュリティ設定を変更する前に慎重[](enable-features-office-365.md)に確認し、既定のセキュリティ設定に変更を加える前にコンプライアンスへの影響を考慮することをお勧めします。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>既定の Microsoft 365 Government - GCC セキュリティ設定を変更するかどうかを決定し、変更の影響を最初に把握します。</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>手順 4. どの機能が現在使用できないか、既定で無効になっているかについて説明します。

政府機関向けクラウドのお客様の要件に対応するために、Government - Microsoft 365 プランと GCCプランEnterpriseがあります。 使用できる機能については、次の表を参照してください。

[Microsoft Teamsの説明](/office365/servicedescriptions/teams-service-description)

> [!Note]
> GCC クラウドで他のワークロードを完全に利用できると、追加の統合作業が完了すると、Teams で使用できます。


|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>組織のニーズTeams機能セットを満たすかどうかを決定します。</li></ul> |

## <a name="step-5-plan-for-governance"></a>手順 5. ガバナンスの計画

ガバナンスの要件とそれらを満たす方法を決定します。 詳細については[、「Teams ガバナンスの](plan-teams-governance.md)計画」を参照してください。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>ガバナンスの要件を決定し、文書化します。このガイドラインは、「Teams でのガバナンスの計画」[のガイドラインに従Teams。](plan-teams-governance.md)</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>手順 6. コラボレーションTeamsをデプロイする

Microsoft 365 Government – GCC にオンボードした後は、「Microsoft Teams をロールアウトする方法」で説明されている推奨されるデプロイ パス[に従Microsoft Teams。](./deploy-overview.md) 必ず、導入および変更管理チームと新しいTeamsしてください。

[また、FastTrack または選択したパートナーと](https://www.microsoft.com/fasttrack)一緒にサービスをオンボードできます。

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>手順 7. 会議Teams音声用のビデオを展開する

また、幅広い関係者グループとTeamsを使用して、会議やクラウド音声機能の展開計画[を開始する場合にも最適な時間です](./cloud-voice-landing-page.md)。