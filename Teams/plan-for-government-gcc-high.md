---
title: Microsoft 365Government - GCC 高デプロイ
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: IT のプロが、米国政府の規制Office 365データを処理するエンティティでのデプロイを支援するガイダンスです。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34ef18970aa601c359aacbcfd8239d9fca2419d7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625979"
---
# <a name="plan-for-office-365-government---gcc-high-deployments"></a>Office 365 Government - GCC High デプロイの計画

このガイダンスは、米国連邦政府の機関または政府の規制や要件の対象となるデータを処理するその他のエンティティで Office 365 の展開を推進している IT プロを対象とします。これらの要件を満たすために Office 365 Government – GCC High の使用が適切です。

> [!NOTE]
> 組織が既に Office 365 Government – GCC の高い資格要件を満たし、プログラムに適用され、プログラムに同意されている場合は、手順 1 と 2 をスキップして、手順 3 に直接進みます。

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-high-and-meets-eligibility-requirements"></a>手順 1. 組織が高いOffice 365 Government必要GCC、適格性要件を満たしていることを確認します。 

Office 365 Government - GCC High 環境は、クラウド サービスに関する米国政府の要件に準拠しています。 組織は、Office 365 の機能を利用できるだけでなく、Office 365 Government – GCC High に固有の機能を利用できます。

- 組織の顧客コンテンツは、Microsoft の商用サービスの顧客コンテンツOffice 365分離されます。
- 組織の顧客コンテンツは米国内に保存されます。
- 組織の顧客コンテンツへのアクセスは、Microsoft の担当者に限定されます。
- Office 365 Government – GCC High は、米国の公的機関のお客様に必要な認定と認定に準拠しています。

米国政府のお客様向け Office 365 Government – GCC High オファリングの詳細については、「Office 365 Government[プラン](https://products.office.com/government/compare-office-365-government-plans)」を参照してください。適格性要件を[含む](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements))。

米国[Office 365サービス](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)の説明では、米国内のコンプライアンス要件を満たしていることを中心にプラットフォームの利点について説明します。


> [!Tip]
> サービスの説明の情報のテーブルを Excel ブックに転送し、2 つの列を追加することができます。組織 **の Y/N** に関連し、組織の **Y/N** のニーズを満たします。 その後、この一覧を同僚と確認して、このサービスが組織のニーズを満たしたと確認できます。


|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>組織に適Office 365 Government - GCC高を選択するかどうかを決定します。</li><li>組織が資格要件を満たしていることを確認します。</li></ul> |

> [!Note]
> Office 365 Government - GCC High は米国でのみ使用できます。 米国政府以外のお客様は、複数のプラン[からOffice 365 Governmentできます](https://products.office.com/en/government/compare-office-365-government-plans)。

## <a name="step-2-apply-for-office-365-government---gcc-high"></a>手順 2. Office 365 Government - GCC High に申し込む

このサービスが組織に正しいと決定した後、このサービスに適用 [するプロセスを開始します](https://products.office.com/government/eligibility-validation)。


## <a name="step-3-understand-office-365-government---gcc-high-default-security-settings"></a>手順 3. Office 365 Government - GCCセキュリティ設定の高い設定について説明します。

管理者とセキュリティ設定を変更する前に慎重[](enable-features-office-365.md)に確認し、既定のセキュリティ設定に変更を加える前にコンプライアンスへの影響を考慮することをお勧めします。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>既定の Office 365 Government - GCC セキュリティの高い設定を変更して、変更の影響を最初に把握する必要があるかどうかを決定します。</li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---gcc-high"></a>手順 4. Teams Office 365 Government - GCC High で現在使用できる機能をGCCする

政府機関向けクラウドのお客様の要件に対応するために、Enterprise プランの Teams - Office 365 Government - GCC High と Teams にはいくつかの違いがあります。 使用できる機能については、次の表を参照してください。

[Microsoft Teamsサービスの説明](/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a>手順 5. ガバナンスの計画

ガバナンスの要件とそれらを満たす方法を決定します。 詳細については[、「Teams ガバナンスの計画](plan-teams-governance.md)」を参照してください。

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|判断ポイント |<ul><li>ガバナンスの要件を決定し、文書化します。このガイドラインは、「Teams でのガバナンスの計画」[のガイドラインに従Teams。](plan-teams-governance.md) </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a>手順 6. コラボレーションTeamsをデプロイする

Office 365 Government – GCC High にオンボードした後は、「Microsoft Teams のロールアウト方法」で説明されている推奨されるデプロイ[パスに従Microsoft Teams。](./deploy-overview.md) 必ず、導入および変更管理チームとチーム のチャンピオンTeamsしてください。

サービスの利用を開始[FastTrack](https://www.microsoft.com/fasttrack)パートナーと一緒に作業を行う方法も可能です。
