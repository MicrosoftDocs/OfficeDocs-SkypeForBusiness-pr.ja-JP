---
title: Microsoft 365 Government - GCCデプロイ
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: IT 担当者が米国政府の規制の対象となるデータを処理するエンティティでのMicrosoft 365展開を推進するためのガイダンス
ms.localizationpriority: medium
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
ms.openlocfilehash: a55c7440b7d3183e93391ecc0e4f8781ba7b690f
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013301"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Microsoft 365 Government - GCCデプロイを計画する

このガイダンスは、米国連邦政府、州、地域、部族、または政府機関の規制や要件の対象となるデータを処理する他のエンティティでMicrosoft 365の展開を推進している IT 担当者向けであり、Microsoft 365 Government - GCCの使用はこれらの要件を満たすのに適しています。 新しい 2020 年 3 月 26 日: GCCのダウンロード可能な[クイック スタート ガイド](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)をお見逃しなく。

> [!IMPORTANT]
> Microsoft Teams、オンライン通話や音声/ビデオ会議が急増しています。これは、コロナウイルス (COVID-19) のパンデミックにより発生しています。<br/>
> 
>通話の前例のない増加に対応し、継続性と可用性を確保するために、Microsoft では、オーディオ/ビデオ サーバー Microsoft Teams GCC、商用データセンターと政府機関のデータセンターの処理能力を活用することを許可しています。<br/>
> 
>これらのオーディオ/ビデオ サーバーは、米国内の Microsoft Azure FedRAMP High 認定境界サーバー内に存在し、顧客コンテンツを格納しません。 ただし、これらのサーバーは通話や会議用のオーディオとビデオを処理しており、この中間期間中はコマーシャル スタッフの下で動作しています。<br/>
> 
>資格のあるスクリーニングされた担当者は、これらのサーバーに対する対話型ログオンを確認することで、顧客データへの潜在的なアクセスについてこれらのサーバーを監視しています。 有資格者は、お客様のコンテンツにアクセスするためのGCC要件を満たしています。 スクリーニング要件の詳細については、[GCCサービスの説明](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)を参照してください。<br/>
> 
>このような特別な時期にサービスを確実に利用し、信頼性を確保するための措置を講じ、サポートをいただき、ありがとうございます。<br/>


> [!NOTE]
> 組織が既に Microsoft 365 Government - GCC資格要件を満たしており、プログラムに申請して受け入れられた場合は、手順 1 と手順 2 をスキップし、手順 3 に直接進むことができます。 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>手順 1. 組織Microsoft 365政府機関 - GCCが必要であり、資格要件を満たしているかどうかを判断します。 

Microsoft 365政府機関 - GCC環境は、FedRAMP Moderate を含むクラウド サービスに対する米国政府の要件、および犯罪の司法および連邦税情報システム (CJI および FTI データ型) の要件への準拠を提供します。

組織は、Microsoft 365の機能を楽しむだけでなく、Microsoft 365 Government - GCCに固有の次の機能の恩恵を受けています。

-   組織の顧客コンテンツは、Microsoft からの商用Microsoft 365 サービスの顧客コンテンツから論理的に分離されます。
-   組織の顧客コンテンツは、米国内に格納されます。
-   組織の顧客コンテンツへのアクセスは、スクリーニングされた Microsoft 担当者に限定されます。
-   Microsoft 365政府機関 - GCCは、米国の公的機関のお客様に必要な認定と認定に準拠しています。

米国政府機関のお客様向けのMicrosoft 365政府機関向けGCCオファーの詳細については、[資格要件](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)など[、Microsoft 365政府機関のプラン](https://products.office.com/government/compare-office-365-government-plans)を参照してください。

[Microsoft 365米国政府機関サービスの説明](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)では、米国内のコンプライアンス要件を満たすことを中心としたプラットフォームの利点について説明しています。

> [!Tip]
> サービスの説明の情報テーブルをExcelブックに転送し、2 つの列を追加することができます。**組織の Y/N に関連** し、**組織の Y/N のニーズを満たします**。 次に、この一覧を同僚と確認して、このサービスが組織のニーズを満たしていることを確認できます。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![判断ポイントを表すアイコン。](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Microsoft 365政府機関 - GCCが組織に適しているかどうかを決定します。</li><li>組織が資格要件を満たしていることを確認します。</li></ul> |

> [!Note]
> Microsoft 365 Government - GCCは、米国でのみ使用できます。 米国以外の政府機関のお客様は、いくつかの[Microsoft 365政府機関の計画](https://products.office.com/en/government/compare-office-365-government-plans)から選択できます。


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>手順 2. Microsoft 365政府機関に申請する - GCC

このサービスが組織に適していると判断したら、 [ここでこのサービスに申し込むプロセスを](https://products.office.com/government/eligibility-validation)開始します。

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>手順 3. 政府機関 - 既定のセキュリティ設定GCC Microsoft 365理解します。

管理者 [とセキュリティ設定](enable-features-office-365.md) を変更する前に注意深く確認し、既定のセキュリティ設定を変更する前にコンプライアンスへの影響を検討することをお勧めします。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![判断ポイントを表すアイコン。](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>既定のMicrosoft 365 Government - GCCセキュリティ設定のいずれかを変更するかどうかを決定し、最初に行う可能性のある変更の影響を理解するように解決します。</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>手順 4. 既定では、現在使用できない機能または無効になっている機能について説明します。

政府機関向けクラウドのお客様の要件に対応するために、Microsoft 365 Government - GCCプランとEnterpriseプランにはいくつかの違いがあります。 使用可能な機能を確認するには、次の表を参照してください。

[Microsoft Teamsサービスの説明](/office365/servicedescriptions/teams-service-description)

> [!Note]
> 他のワークロードがGCC クラウドで完全に利用できるようになると、追加の統合作業がすべて完了すると、Teamsで利用できるようになります。


|&nbsp;|&nbsp;|
|-----------|------------|
| ![判断ポイントを表すアイコン。](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Teams機能セットが組織のニーズを満たしているかどうかを決定します。</li></ul> |

## <a name="step-5-plan-for-governance"></a>手順 5. ガバナンスの計画

ガバナンスの要件と、それを満たす方法を決定します。 詳細[については、「Teamsのガバナンスの計画](plan-teams-governance.md)」を参照してください。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![判断ポイントを表すアイコン。](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Teamsのガバナンス計画のガイドラインに従って、[ガバナンス要件を](plan-teams-governance.md)決定して文書化します。</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>手順 6. コラボレーション用にTeamsをデプロイする

Microsoft 365 Government – GCCにオンボードしたら、「Microsoft Teamsを[ロールアウトする方法](./deploy-overview.md)」で説明されている推奨されるデプロイ パスに従います。 導入および変更管理チームとTeamsのチャンピオンと連携してください。

また、[FastTrack](https://www.microsoft.com/fasttrack)または選択したパートナーと連携してサービスをオンボードすることもできます。

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>手順 7. 会議と音声のTeamsを展開する

また、幅広い関係者グループとTeamsを使用して、会議や[クラウド音声機能](./cloud-voice-landing-page.md)の展開の計画を開始する絶好の機会でもあります。