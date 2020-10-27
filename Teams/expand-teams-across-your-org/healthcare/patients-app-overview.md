---
title: 'Teams 管理者用の患者アプリ '
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
description: Teams 管理者用の患者アプリ
ms.openlocfilehash: b15336f939cefefeaebb77c2ca92b73373bc249e
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766930"
---
# <a name="patients-app-overview"></a>患者アプリの概要

> [!IMPORTANT]
> **2020年10月30日の有効な患者アプリは廃止され、ユーザーは Teams app store からインストールできなくなります。今すぐ Teams の [リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) を使い始めることをお勧めします。**
>
>患者のアプリデータは、チームをバックアップする Office 365 グループのグループメールボックスに格納されます。 患者のアプリが廃止されると、そのアプリに関連付けられたデータはすべてこのグループに保持されますが、ユーザーインターフェイスを使ってアクセスすることはできなくなります。 現在のユーザーは、 [リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)を使ってリストを再作成できます。
>
>[リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)は、すべての Teams ユーザー用にプレインストールされており、すべてのチームとチャネルでタブとして使用できます。 リストを使用すると、正常性チームは、組み込みの [患者] テンプレートを使用して、最初から、または Excel にデータをインポートして、患者リストを作成できます。 組織でのリストアプリの管理方法の詳細については、「 [リストアプリを管理](../../manage-lists-app.md)する」を参照してください。

患者アプリケーションは、Microsoft Teams ストアアプリで、すべての Teams ユーザーが利用できます。 このアプリを使用すると、患者の医療チーム (看護師、医師、ソーシャルワーカーなど) で構成される患者の患者のリストを、ラウンドやさまざまなチーム会議から一般的な患者の監視まで、さまざまなシナリオで確認できます。

このアプリには、次の2つのモードがあります。

- Emr から FHIR に接続する EMR 接続モード。 EMR 接続モードのアプリはプライベートプレビューのままで、お客様または管理者は、microsoft 365 組織に関する情報を含む [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) に microsoft メールをドロップして、アプリへのアクセスを要求することがあります。
- 医療チームが手動で患者情報を追加/取り込みできる手動モード。 アプリケーションは、Teams app store で利用可能で、エンドユーザーはプライベートプレビューでダウンロードすることができます。 アプリは、Teams の [アプリセットアップポリシー](../../teams-app-setup-policies.md) を使用して、ユーザーの特定のセクションに制限することができます。 アプリへのアクセスを取得するには、テナントがテクノロジ導入プログラムに含まれている必要があります (タップ)。 [Teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com)でメールを削除して、アクセス権を要求するプロセスを開始してください。

## <a name="usage-example"></a>使用例

医療 wards の各シフトでの丸めセッション中に、clinicians は nursing ステーションで収集して、の患者との進行状況に関する最新の更新について話し合うことができます。  また、重要な指標 (医療、患者の医療記録での明示的なものではありません) を強調表示し、診断に基づいて患者が適切なグライドパス上にいることを確認します。 このような患者を丸めるために、クレジットの追加により、すべての clinicians が追加され、患者リストに患者が追加されるようになります。 このラウンドでは、患者との間の看護師とその他のケア givers によって、モバイルデバイス上の Microsoft Teams と患者アプリの情報が更新され、デバイス上の他のユーザーがその更新内容とメモを確認して、同期を保つことができます。1日に2回、シフトの開始時と終了時には、患者リストを超えて患者の一覧を表示し、患者のアプリを使って患者の顔を見ながら、大きなディスプレイ画面で患者のアプリを使って情報を共有することができます。 場合によっては、特定の clinicians が、それらのチーム会議にリモートでダイヤルインしても、ディスカッションの一部となることがあります。

## <a name="configure-patients-app"></a>患者のアプリを設定する

EMR モードの患者アプリを使用するように環境を準備する方法について詳しくは、「 [Microsoft Teams への電子医療記録の統合](patients-app.md)」をご覧ください。 また、組織で患者のアプリを有効にするには、「 [Microsoft Teams でアプリセットアップポリシーを管理](../../teams-app-setup-policies.md) する」を参照する必要があります。

エンドユーザーが患者アプリにアクセスして自分が所有または管理しているチームにインストールする方法については、「 [Microsoft Teams の患者の概要](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393)」を参照してください。

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>よく寄せられる質問 (FAQ)

**患者のアプリデータはどこに保存されますか?**

エンドユーザーによって [患者] アプリに入力されたすべてのデータ (たとえば、列/フィールドスキーマ、リストとリストアイテム (患者) に入力された実際のデータ) は、セキュリティで保護された、互換性のある Exchange Online インフラストラクチャに格納されます。 すべてのデータは、チームに関連付けられているグループメールボックスに格納されます。 このアーキテクチャにより、患者アプリは、データ常駐サービス、行政機関向けクラウドサポート (将来の予定)、および eDiscovery サポートなどのその他のコンプライアンス/情報保護機能を簡単に満たすことができます。 患者アプリは、チームのスコープで動作します。 チームごとにアプリのインスタンスをインストールする必要があります。

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**患者アプリの入手方法を教えてください。**

管理者によって、自分の組織に対して患者のアプリが有効になっている場合、すべてのエンドユーザーは Teams app store にアクセスして、自分がメンバーになっているチームに患者アプリを追加することができます。 詳細については、「 [Microsoft Teams でアプリセットアップポリシーを管理](../../teams-app-setup-policies.md)する」を参照してください。

**自分のワード/ユニットの動作によって、チーム内に複数のインスタンスを含めることはできますか?**

現時点では、特定のチームに対してのみ、または [全般] チャネルにのみインストールできます。 ただし、アプリ内では、複数のチャネルまたは分離シナリオに対応するために複数のリストを作成できます。 既定では、チームのすべてのメンバーは、[全般] チャネルの [患者] タブにアクセスできます。 

**患者アプリからすべてのデータをエクスポートすることはできますか?**
現時点ではできませんが、この機能は近日中に公開されます。 

**このアプリは PHI に対応しているため、不正アクセスや規制への準拠を防ぐ監査もありますか?**

はい、あります。 患者のアプリで Microsoft Teams ユーザーによって実行されるすべての UI 操作が監査され、セキュリティ/コンプライアンスセンターで利用可能になります。 詳細については、「 [患者アプリの監査ログ](patients-audit.md)」で説明します。

## <a name="related-topics"></a>関連項目

[電子医療記録を Microsoft Teams に統合する](patients-app.md)
