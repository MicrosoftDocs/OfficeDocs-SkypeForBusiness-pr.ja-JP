---
title: Microsoft 365 Government-GCC 展開
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 米国政府規制の対象となるデータを処理するエンティティで Microsoft 365 の展開を推進するための IT 担当者向けガイダンス
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
ms.openlocfilehash: e40f511aedfed2423e04ece74a9c2c7f370acb74
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085611"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Microsoft 365 Government-GCC 展開を計画する

このガイダンスは、米国連邦、州、地方、tribal、または territorial 政府機関の法人、州、地方、、または政府機関の団体またはその他の法人で、これらの要件を満たすために Microsoft 365 Government-GCC の使用が適している場合に、Microsoft 365 の展開を行う IT プロフェッショナルを対象としています。 2020年3月 26 [日: GCC 向けのダウンロード可能なクイックスタートガイド](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)をお見逃しなく。

> [!IMPORTANT]
> Microsoft Teams では、coronavirus (COVID-19) pandemic のため、オンライン通話、音声/ビデオ会議に大きなスパイクが発生しています。<br/>
> 
>優れた通話の増加に対応し、継続性と可用性を確保するために、microsoft Teams の音声/ビデオサーバは、microsoft Teams の商用データセンターと行政機関のデータセンターでの処理能力を活用できるようになります。<br/>
> 
>これらのオーディオ/ビデオサーバーは、米国の Microsoft Azure FedRAMP 高認定境界サーバー内に存在し、お客様のコンテンツは保存しません。 ただし、このようなサーバーは、通話や会議のための音声とビデオを処理しており、この中間的な間、当社の商用スタッフで動作しています。<br/>
> 
>認定された審査担当者は、これらのサーバーの対話的なログ出力を確認して、顧客データにアクセスできる可能性があるサーバーを監視しています。 認定担当者は、お客様のコンテンツへのアクセスに必要な GCC の要件を満たしています。 審査の要件の詳細については、「 [GCC サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)」を参照してください。<br/>
> 
>お客さまのサポートにご協力いただき、ありがとうございました。 skype のサービスは、これらの特別なタイミングで利用可能で信頼できることを確認するための措置となります。<br/>


> [!NOTE]
> 組織が既に Microsoft 365 Government-GCC の資格要件を満たし、プログラムに受け入れられている場合は、手順1と2をスキップして、手順3に進みます。 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>手順1 組織に Microsoft 365 Government-GCC が必要かどうか、および資格要件を満たしているかどうかを確認します。 

Microsoft 365 Government-GCC 環境は、お客さまのクラウドサービスに関する米国政府の要件に準拠します。これには、FedRAMP の低品質、刑事司法および連邦税情報システム (CJI と FTI のデータ型) が含まれます。

Microsoft 365 の機能を活用できるように、組織では、Microsoft 365 Government-GCC に固有の次の機能を利用することができます。

-   組織の顧客のコンテンツは、Microsoft の商用 Microsoft 365 サービスの顧客のコンテンツから論理的に分離されています。
-   組織の顧客コンテンツは、米国内に保存されています。
-   組織のお客様のコンテンツへのアクセスは、Microsoft のユーザーに制限されています。
-   Microsoft 365 Government-GCC は、米国公的機関のお客様に必要な認定および accreditations に準拠しています。

Microsoft [365 government](https://products.office.com/government/compare-office-365-government-plans)のお客様向けの Microsoft 365 GOVERNMENT-GCC 製品の詳細については、「 [特典の要件](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)」も参照してください。

[Microsoft 365 US Government service の説明](https://technet.microsoft.com/library/mt774581.aspx)では、プラットフォームの利点について説明します。これは、米国内でのコンプライアンス要件を満たしています。

> [!Tip]
> サービスの説明に記載されている情報の表を Excel ブックに転送して、**組織****のニーズに応じ** て2つの列を追加することができます。 次に、このリストを同僚と確認して、このサービスが組織のニーズを満たしていることを確認します。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>組織に対して Microsoft 365 Government-GCC が適切であるかどうかを決定します。</li><li>組織が資格要件を満たしていることを確認します。</li></ul> |

> [!Note]
> Microsoft 365 Government-GCC は米国でのみ利用可能です。 米国政府以外のお客様は、 [Microsoft 365 Government のプラン](https://products.office.com/en/government/compare-office-365-government-plans)から選ぶことができます。


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>手順2 Microsoft 365 Government-GCC に適用する

このサービスが組織に適していると判断された場合は、 [ここでこのサービスの適用](https://products.office.com/government/eligibility-validation)プロセスを開始します。

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>手順3 Microsoft 365 Government-GCC の既定のセキュリティ設定について説明します。

[管理とセキュリティの設定](enable-features-office-365.md)を変更する前に慎重に確認し、コンプライアンスへの影響を考慮して、既定のセキュリティ設定を変更することをお勧めします。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Microsoft 365 Government の既定のセキュリティ設定を変更するかどうかを決定します。解決するには、変更の影響を最初に理解する必要があります。</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>手順4。 現在、どの機能が既定で利用できないか、無効になっているかを理解する。

政府機関向けクラウドのお客様の要件に対応するため、Microsoft 365 Government-GCC とエンタープライズのプランにはいくつかの違いがあります。 使用できる機能については、次の表を参照してください。

[Microsoft Teams サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> GCC クラウドで他の作業負荷が完全に利用できるようになると、その他の統合作業が完了したときにチームで利用できるようになります。


|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Teams 機能セットが組織のニーズを満たすかどうかを決定します。</li></ul> |

## <a name="step-5-plan-for-governance"></a>手順5 ガバナンスの計画

ガバナンスの要件と、それらをどのように満たすかを決定します。 詳細については、「 [Teams のガバナンスの計画」](plan-teams-governance.md) を参照してください。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>[チームのガバナンス計画](plan-teams-governance.md)のガイドラインに従って、ガバナンス要件を特定して文書化します。</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>手順6 チームをコラボレーションのために展開する

Microsoft 365 Government – GCC に onboarded したら、「 [Microsoft Teams をロールアウトする方法](How-to-roll-out-teams.md)」に記載されている展開の推奨パスに従います。 お客様の導入と変更管理チームやチームのチャンピオンに協力してください。

また、 [Fasttrack](https://www.microsoft.com/fasttrack) または選択したパートナーと連携してサービスを稼働させることもできます。

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>手順7 会議と音声のチームを展開する

これは、より幅広いステークホルダーグループで Teams を使用して、会議や [クラウド音声機能](cloud-voice-deployment.md)のロールアウトの計画を開始するのに非常に時間がかかることです。

