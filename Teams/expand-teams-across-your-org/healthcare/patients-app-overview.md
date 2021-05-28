---
title: 'Teams 管理者向けの患者アプリ '
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Teams 管理者向けの患者アプリの詳細
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2302f117564e1dd00a6f238ca23a8e36c63ae554
ms.sourcegitcommit: e6e6a2a85ff376f97a3af3548e13d1273fa84a52
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2021
ms.locfileid: "52697844"
---
# <a name="patients-app-overview"></a>患者アプリの概要

> [!NOTE]
> 2020 年 10 月 30 日より、患者アプリは廃止され、Teams の[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)に置き換えられました。 患者アプリのデータは、チームを支援する Office 365 グループのグループ メールボックスに保存されます。 患者アプリに関連付けられているすべてのデータはこのグループに保持されますが、ユーザー インターフェイスからアクセスすることはできなくなります。 ユーザーは、[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)を使用してリストを再作成できます。
>
>リストを使用すると、医療機関のケア チームは、ラウンドや学際的なチーム会議から一般的な患者の監視に至るまでのシナリオで患者リストを作成できます。 開始するには、リストの患者テンプレートを確認してください。 組織でリスト アプリを管理する方法の詳細については、「[リスト アプリの管理](../../manage-lists-app.md)」を参照してください。

患者アプリケーションは、すべての Teams ユーザーが利用できる Microsoft Teams ストア アプリです。 このアプリを使用すると、臨床従事者 (看護師、医師、ソーシャル ワーカーなど) で構成される患者医療チームが、ラウンドや学際的なチーム会議から一般的な患者の監視に至るまでのシナリオで、患者のリストをキュレートして確認できます。

アプリには 2 つのモードがあります。

- FHIR を介して EMR に接続する EMR 接続モード。 EMR 接続モード アプリはプライベート プレビューであり、関心のある顧客または管理者は、Microsoft 365 組織に関する情報を記載したメールを [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) にドロップすることにより、アプリへのアクセスを要求できます。
- 医療チームが患者情報を手動で追加/取り込むことができる手動モード。 アプリケーションは、Teams アプリ ストアで入手し、エンド ユーザーがプライベート プレビューでダウンロードできます。 Teams で[アプリのセットアップ ポリシー](../../teams-app-setup-policies.md)を使用すると、アプリをユーザーの特定のセクションに制限できます。 アプリにアクセスするには、テナントがテクノロジ採用プログラム (TAP) に参加している必要があります。 アクセスを要求するプロセスを開始するには、[teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) にメールをお送りください。

## <a name="usage-example"></a>使用例

病棟のシフトごとのラウンド セッション中に、臨床医が看護ステーションに集まり、病棟の患者と現在の進行状況について話し合います。  重要な測定基準 (必ずしも医学的である必要はなく、患者の医療記録において明示的である必要はありません) を強調表示し、患者が診断に基づいて退院するための正しいグライド パスにいることを確認します。 これらの患者をラウンドするために、担当看護師はチームに患者アプリを設定し、そこにすべての臨床医が追加され、患者は患者リストに追加されます。 ラウンド中、患者の看護師やその他の介護者は、モバイル デバイスで Microsoft Teams と患者アプリにアクセスし、デバイスで関連する患者情報を更新します。その後、医療チームの他の全員がそれらの更新とメモを確認して、 同期します。1 日 2 回、シフトの開始時と終了時に、患者リストを確認し、患者アプリを使用して、現状を把握し、大きなディスプレイ画面の患者アプリを使用して各患者に関する情報を共有する、学際的なチーム会議もあります。 しばしば、特定の臨床医は、これらの Teams の会議にリモートでダイヤルインして、ディスカッションに参加することもあります。

## <a name="configure-patients-app"></a>患者アプリを構成する

組織[で Patients アプリを有効にするには、「Microsoft Teams](../../teams-app-setup-policies.md)のアプリ セットアップ ポリシーの管理」を参照してください。

エンド ユーザーが患者アプリにアクセスして、所有または管理するチームにインストールする方法については、「[Microsoft Teams 患者アプリの使用を開始する](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393)」を参照してください。

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>よく寄せられる質問 (FAQ)

**患者アプリのデータはどこに保存されますか?**

列/フィールド スキーマ、リストおよびリスト アイテム (患者など) に入力された実際のデータを含む、エンド ユーザーが患者アプリに入力したすべてのデータは、安全で準拠した Exchange Online インフラストラクチャに保存されます。 すべてのデータは、チームに関連付けられているグループ メールボックスに保存されます。 このアーキテクチャにより、患者アプリは、データの常駐、政府のクラウド サポート (将来的に予定)、および電子情報開示サポートなどの他のコンプライアンス/情報保護機能を簡単に実行できます。 患者アプリはチームの範囲で動作します。 チームごとにアプリのインスタンスをインストールする必要があります。

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**患者アプリはどこから入手できますか?**

管理者が患者アプリを組織で有効にしている場合、すべてのエンド ユーザーは Teams アプリ ストアにアクセスして、患者アプリをメンバーのチームに追加できます。 詳細については、「[Microsoft Teams でアプリのセットアップ ポリシーを管理する](../../teams-app-setup-policies.md)」を参照してください。

**病棟/ユニットの運用方法として、チームに患者アプリの複数のインスタンスを含めることはできますか?**

現在、与えられたチームにインストールできるのは、患者アプリのインスタンス 1 つだけで、全般チャネルにのみインストールできます。 ただし、アプリ内で複数のリストを作成して、マルチチャネルまたは分離/区分のシナリオに対応できます。 既定では、チームのすべてのメンバーが全般チャネルの [患者] タブにアクセスできます。 

**患者アプリからすべてのデータをエクスポートできますか?**
現在はありませんが、この機能はまもなく登場します。 

**このアプリは PHI に対応しているので、不正アクセスを防ぎ、規制に準拠するための監査はありますか?**

はい、あります。 Microsoft Teams ユーザーが患者アプリで実行するすべての UI アクションは監査され、セキュリティ/コンプライアンス センターで利用できます。 詳細は、「[患者アプリの監査ログ](patients-audit.md)」で説明されています。

