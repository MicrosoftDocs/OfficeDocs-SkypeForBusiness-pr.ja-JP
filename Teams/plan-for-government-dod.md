---
title: Office 365 Government - DoD デプロイ
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: IT のプロが、米国政府の DoD 規制Office 365データを処理するエンティティでのデプロイを支援するガイダンスです。
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
ms.openlocfilehash: dfe5daabc060a3d6a6e83ba78d90a33b35ec4398
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58730466"
---
# <a name="plan-for-office-365-government---dod-deployments"></a>DoD デプロイOffice 365 Government計画する

このガイダンスは、Office 365 Government – DoD の使用がこれらの要件を満たすのに適している、政府の規制や要件の対象となるデータを処理する米国連邦政府機関または他のエンティティへの Office 365 の展開を推進している IT プロを対象とします。

> [!NOTE]
> 組織が既に Office 365 Government – DoD の資格要件を満たし、プログラムに適用され、プログラムに同意されている場合は、手順 1 と 2 をスキップし、手順 3 に直接進みます。

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---dod-and-meets-eligibility-requirements"></a>手順 1. 組織が DoD を使用してOffice 365 Government要件を満たしていることを確認します。 

Office 365 Government - DoD 環境は、クラウド サービスに関する米国政府の要件に準拠しています。 組織は、Office 365 の機能を利用できるだけでなく、Office 365 Government – DoD に固有の機能を利用できます。

- 組織の顧客コンテンツは、Microsoft の商用サービスの顧客コンテンツOffice 365分離されます。
- 組織の顧客コンテンツは米国内に保存されます。
- 組織の顧客コンテンツへのアクセスは、Microsoft の担当者に限定されます。
- Office 365 Government – DoD は、米国の公的機関のお客様に必要な認定と認定に準拠しています。

米国政府のお客様向け Office 365 Government – DoD オファリングの詳細については[](https://products.office.com/government/compare-office-365-government-plans)、Office 365 Government プランに関するページを参照してください。利用資格要件も[含め)。](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)

米国[Office 365サービス](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)の説明では、米国内のコンプライアンス要件を満たしていることを中心にしたプラットフォームの利点について説明します。


> [!Tip]
> サービスの説明の情報のテーブルを Excel ブックに転送し、2 つの列を追加できます。組織 **の Y/N** に関連し、組織の **Y/N** のニーズを満たします。 その後、この一覧を同僚と確認して、このサービスが組織のニーズを満たしたと確認できます。


|    |     |
|-----------|------------|
| ![決定ポイントを示すアイコン。](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>組織にOffice 365 Government - DoD が適切かどうかを決定します。</li><li>組織が資格要件を満たしていることを確認します。</li></ul> |

> [!Note]
> Office 365 Government - DoD は米国でのみ使用できます。 米国政府以外のお客様は、複数のプラン[からOffice 365 Governmentできます](https://products.office.com/en/government/compare-office-365-government-plans)。

## <a name="step-2-apply-for-office-365-government---dod"></a>手順 2. Office 365 Government - DoD に申し込む

このサービスが組織に正しいと決定した後、このサービスに適用 [するプロセスを開始します](https://products.office.com/government/eligibility-validation)。


## <a name="step-3-understand-office-365-government---dod-default-security-settings"></a>手順 3. [Office 365 Government - DoD の既定のセキュリティ設定について説明します。

管理者とセキュリティ設定を変更する前に慎重[](enable-features-office-365.md)に確認し、既定のセキュリティ設定に変更を加える前にコンプライアンスへの影響を考慮することをお勧めします。

|    |     |
|-----------|------------|
| ![決定ポイントを示すアイコン。](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>既定の Office 365 Government - DoD セキュリティ設定を変更して、変更の影響を最初に把握する必要があるかどうかを決定します。</li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---dod"></a>手順 4. DoD Teamsで現在使用できる機能Office 365 Government理解する

政府機関向けクラウドのお客様の要件に対応するために、Office 365 Government - DoD の Teams と Enterprise プランの Teams にはいくつかの違いがあります。 使用できる機能については、次の表を参照してください。

[Microsoft Teamsの説明](/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a>手順 5. ガバナンスの計画

ガバナンスの要件とそれらを満たす方法を決定します。 詳細については[、「Teams ガバナンス](plan-teams-governance.md)の計画」を参照してください。

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|判断ポイント |<ul><li>ガバナンス要件を決定し、文書化します。このドキュメントの「ガバナンスの計画」のガイドライン[に従Teams。](plan-teams-governance.md) </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a>手順 6. コラボレーションTeamsをデプロイする

Office 365 Government – DoD にオンボードした後は、「Office 365 Government を展開する方法」に示されている推奨されるデプロイ パス[に従Microsoft Teams。](./deploy-overview.md) 必ず、導入および変更管理チームと新しいTeamsしてください。

サービスのオンボードには[、FastTrack](https://www.microsoft.com/fasttrack)パートナーと一緒に作業を行う方法があります。

> [!NOTE]
> DOD 環境Teams Mac クライアントはまだサポートされていません。