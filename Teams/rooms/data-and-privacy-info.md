---
title: データとプライバシー情報
author: altsou
ms.author: altsou
manager: serdars
ms.date: 06/01/2022
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: データとプライバシー情報
f1keywords: Microsoft Teams Rooms Managed Service Data and Privacy Information
ms.openlocfilehash: dd80718da862be02b42a5cf18334c89e86c3807c
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438421"
---
# <a name="approach"></a>手法

Microsoft Teams Roomsマネージド サービスを使用しているお客様は、最も価値の高い資産であるデータをMicrosoftに委託します。 彼らは、そのプライバシーが保護され、期待と一致する方法でのみ使用されることを信頼しています。

このテクノロジは、プライバシー プロセスに従って、サービスを効果的に実行するデータを収集して使用する際の顧客の約束に準拠していることを確認します。
## <a name="data-collection-and-privacy"></a>データ収集とプライバシー

 Microsoft Teams Roomsマネージド サービスは、デバイスの監視、顧客コンテンツ データの収集、管理者としてデバイスへのリモート アクセスと管理を行います。 収集されるデータは、登録済みルームで特定された正常性、根本原因、軽減の問題を監視するために必要な情報に限定されます。 収集される特定のデータは、個々のユーザーではなく、会議室アカウントに固有です。

> [!Note]
> 個々のユーザーへの偶発的な参照は、デバイスの使用中にアクティビティ ログに記録される場合があります。

## <a name="who-can-access-data"></a>データにアクセスできるユーザー

マネージド サービスは、不正なアクセスや未承認のユーザーによる使用から顧客データを保護するための強力な対策を講じます。 これらの措置には、Microsoft担当者と下請け業者によるアクセスの制限が含まれます。

## <a name="zero-standing-access-data-storage"></a>ゼロ スタンディング アクセス データ ストレージ

マネージド サービスは、ゼロ スタンディング アクセスの原則を通じて、組織内外の悪意のあるアクターからの特権アクセスを持つアカウントに関連するリスクを軽減します。 この原則により、Managed Services は既定で任意のユーザーが使用できる特権なしで動作できます。 Just-In-Time と Just-Enough-Access の原則と組み合わせることで、セキュリティで保護され、既定で準拠するための堅牢なフレームワークが提供されます。 診断データは、内部ポータルを介してMicrosoft サービス運用チームが利用できます。

## <a name="data-handling"></a>データ処理

Microsoftは、データ転送、ストレージ、使用、保持に関する厳格な基準によって管理されます。 Microsoftには、データ分類に基づいてデータを処理する方法を規制するデータ処理標準ポリシーがあります。

## <a name="technology-description"></a>テクノロジの説明

マネージド サービスは、デプロイの問題を監視、診断、軽減するために、データをMicrosoftに送信します。 例としては、次のようなものがあります。

- デバイスが最新の状態であることを確認する (アプリ、OS、ドライバー、F/W を含む)
- デバイスを使用する準備ができている (サインイン中、正常な状態を報告するすべての周辺機器など) を確認する
- 環境の準備が整っている (アカウントのプロビジョニング、ネットワーク速度が十分に速いなど)
- ハードウェアの問題やインストールの問題 (緩やかなケーブル接続など) が発生する可能性があるかどうかを判断する
- 問題を特定するためのヒューリスティック (過剰な再起動など)

マネージド サービスは、次のアクションを使用してデバイスを管理します。

- ソフトウェアの更新
- 再起動、USB 接続&状態のリセットによる問題の軽減
- 問題の診断に役立つ特定のログを収集する

マネージド サービスは、ソリューション キットからオーディオ、ビデオ、メディア、会議コンテンツを監視または記録しません。

### <a name="service-collected-data-categories"></a>サービスで収集されたデータ カテゴリ
 
|[カテゴリ]|詳細|クエリの理由|
| :- | :- | :- |
|継続的なデータ収集と管理|IP アドレス、会議室アカウントの ID (Exchange、Skype for Business、または Teams)、場所の調整、電子メール、ポータル内でのMicrosoftまたはソフトウェアとの通信|管理下のシステムを識別して接続します。エラーを特定、診断、軽減する。使用状況、分析、分析情報を追跡する。クエリと修復の接続状態|
|アドホック データの収集と管理|イベント ログ情報、診断情報、Windows システム クエリと共にログ ファイルにログインしたルーム ユーザーのユーザー アクティビティ/ID (例: USB デバイスの一覧、電源状態など)|エラーを特定、診断、軽減し、使用状況、分析、分析情報を確認する|

デバイス アクティビティ ログ内の特定の機密データはローカルで編集されます (マネージド サービスによって収集されません)。

- 会議の件名と本文
- 会議出席者の連絡先カード情報 (タイトル、電話番号など)
- 会議 IM メッセージの内容

> [!NOTE]
> マネージド サービスMicrosoft進化するにつれて、特定のデータは変更される可能性があります。

### <a name="enrollment"></a>登録

マネージド サービスは、診断やレポートを含む自動監視およびサポート サービスのためにオンライン ポータルに登録されます。 登録は、デバイスのトラステッド プラットフォーム モジュール (TPM) ベースの公開キーを使用して暗号化されたネットワーク通信によって行われます。

### <a name="unenrollment"></a>登録を解除する

マネージド サービスをアンインストールすると、デバイスの登録を解除できます。 Microsoftは、使用停止中にバックエンド監視からデバイスを削除し、要求に応じて収集されたデータを削除することもできます。
## <a name="compliance"></a>コンプライアンス

製品に取り組むすべてのエンジニアは、セキュリティとプライバシー意識のトレーニングを受ける必要があります。 Microsoftは、すべての担当者がプライバシー要件に対する責任の受け入れを認定することを保証します。

マネージド サービスは、ヨーロッパ (EU)、アジア太平洋 (APAC)、米国 (米国) のデータ センターを通じて、地域のデータ所在地のサポートを提供します。 サービスのお客様は、選択したリージョンのデータ センターに格納されている組織に関連するデータを取得します。

## <a name="more-resources"></a>その他のリソース

Windows セキュリティのMicrosoft Teams Rooms: [[Microsoft Teams for Windows セキュリティ](/microsoftteams/rooms/security-windows)] \
Android のセキュリティに関するMicrosoft Teams Rooms: [Android セキュリティ用Microsoft Teams](/microsoftteams/rooms/security-android) \
Microsoftプライバシーに関する声明:https://aka.ms/privacy \
Microsoftでのデータ管理:https://www.microsoft.com/trust-center/privacy/data-management \
マネージド サービス サービスの説明: [Microsoft Teams Room マネージド サービス](rooms-pro-management.md)
