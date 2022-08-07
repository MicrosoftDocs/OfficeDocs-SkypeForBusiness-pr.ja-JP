---
title: データとプライバシー情報
author: donnah007
ms.author: v-donnahill
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
ms.openlocfilehash: 5799288005a5d30152a6f810c0aa40d451198390
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270302"
---
# <a name="approach"></a>手法

Microsoft Teams Roomsマネージド サービスを使用しているお客様は、Microsoft に最も価値のある資産であるデータを委託します。 彼らは、そのプライバシーが保護され、期待に沿った方法でのみ使用されることを信頼しています。

このテクノロジは、プライバシー プロセスに従って、サービスを効果的に実行するデータの収集と使用に関する顧客の約束に従っていることを確認します。
## <a name="data-collection-and-privacy"></a>データの収集とプライバシー

 Microsoft Teams Rooms Managed Services は、デバイスを監視し、顧客コンテンツ データを収集し、デバイスに管理者としてリモートからアクセスして管理します。 収集されるデータは、登録済みルームで特定された正常性、根本原因、および問題の軽減を監視するために必要な情報に限定されます。 収集される特定のデータは、個々のユーザーではなく、ルーム アカウントに固有です。

> [!Note]
> 個々のユーザーへの偶発的な参照は、デバイスの使用中にアクティビティ ログに記録される場合があります。

## <a name="who-can-access-data"></a>データにアクセスできるユーザー

マネージド サービスは、不正アクセスや不正なユーザーによる使用から顧客データを保護するために強力な手段を講じます。 これらの措置には、Microsoft の担当者と下請け業者によるアクセスの制限が含まれます。

## <a name="zero-standing-access-data-storage"></a>ゼロ スタンディング アクセス データ ストレージ

マネージド サービスは、ゼロ スタンディング アクセスの原則を通じて、悪意のあるアクター (組織の内部と外部の両方) からの特権アクセスを持つアカウントに関連するリスクを軽減します。 この原則により、マネージド サービスは、既定で任意のユーザーが利用できる特権なしで動作できます。 Just-In-Time と Just-Enough-Access の原則と組み合わせることで、セキュリティで保護され、既定で準拠する堅牢なフレームワークが提供されます。 診断データは、内部ポータルを介して Microsoft サービス運用チームが利用できます。

## <a name="data-handling"></a>データ処理

Microsoft は、データ転送、ストレージ、使用、および保持に関する厳格な標準に準拠しています。 Microsoft には、データ分類に基づいてデータを処理する方法を規制するデータ処理標準ポリシーがあります。



## <a name="technology-description"></a>テクノロジの説明

Managed Services は、デプロイ内の問題の監視、診断、軽減を目的として、Microsoft にデータを送信します。 例を次に示します。

- デバイスが最新であることを確認する (アプリ、OS、ドライバー、F/W を含む)
- デバイスを使用する準備ができている (サインインしている、正常な状態を報告するすべての周辺機器など)
- 環境の準備が整っている (アカウントがプロビジョニングされている、ネットワーク速度が十分に速いなど)
- ハードウェアの問題やインストールの問題 (ケーブルの緩みなど) がある可能性があるかどうかを判断する
- 問題を特定するためのヒューリスティック (過剰な再起動など)

マネージド サービスは、次のアクションでデバイスを管理します。

- ソフトウェアの更新
- 再起動による問題の軽減、USB 接続&状態のリセット
- 問題の診断に役立つ特定のログを収集する

マネージド サービスは、ソリューション キットからオーディオ、ビデオ、メディア、会議のコンテンツを監視または記録しません。

### <a name="service-collected-data-categories"></a>サービスで収集されたデータ カテゴリ
 
|[カテゴリ]|詳細|クエリの理由|
| :- | :- | :- |
|継続的なデータ収集と管理|IP アドレス、ルーム アカウントの ID (Exchange、Skype for Business、Teams)、場所の座標、電子メール、Microsoft またはソフトウェアとのポータル内の通信|管理下のシステムを特定して接続する。障害を特定、診断、軽減する。使用状況、分析、分析情報を追跡する。接続状態のクエリと修復|
|アドホック データの収集と管理|イベント ログ情報、ユーザー アクティビティ、ルーム ユーザーのログイン ログ ファイルからの ID、診断情報、Windows システム クエリ (例: USB デバイスの一覧、電源状態など)|障害を特定、診断、軽減し、使用状況、分析、分析情報を確認する|

デバイス アクティビティ ログ内の特定の機密データは、ローカルで (マネージド サービスによって収集されない) やり直されます。

- 会議の件名と本文
- 会議出席者の連絡先カード情報 (タイトル、電話番号など)
- 会議 IM メッセージ コンテンツで

> [!NOTE]
> Microsoft がマネージド サービスを進化させるにつれて、特定のデータは変更される可能性があります。

### <a name="enrollment"></a>登録

マネージド サービスは、診断やレポートなど、自動監視サービスとサポート サービス用にオンライン ポータルに登録されます。 登録は、デバイスのトラステッド プラットフォーム モジュール (TPM) ベースの公開キーを使用して暗号化されたネットワーク通信を介して行われます。

### <a name="unenrollment"></a>登録解除

デバイスの登録を解除するには、マネージド サービスをアンインストールします。 Microsoft は、使用停止中にバックエンド監視からデバイスを削除し、要求に応じて収集されたデータを削除することもできます。
## <a name="compliance"></a>コンプライアンス

製品に取り組むすべてのエンジニアは、セキュリティとプライバシー認識のトレーニングを受ける必要があります。 また、Microsoft は、すべての担当者がプライバシー要件に対する責任の受け入れを認定することを保証します。

マネージド サービスは、ヨーロッパ (EU)、アジア太平洋 (APAC)、米国 (米国) のデータ センターを通じて、地域のデータ常駐サポートを提供します。 サービスのお客様には、選択したリージョンのデータ センターに格納されている組織に関連するデータが含まれます。

## <a name="more-resources"></a>その他のリソース

Microsoft Teams Rooms セキュリティ:/microsoftteams/rooms/security Microsoft Privacy Statement: https://aka.ms/privacyMicrosoft でのデータ管理: https://www.microsoft.com/trust-center/privacy/data-management Managed Services サービスの説明: [Microsoft Teams Room マネージド サービス](microsoft-teams-rooms-premium.md)
