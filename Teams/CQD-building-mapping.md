---
title: 通話品質ダッシュボード (CQD) の建物マップを作成する
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 通話品質ダッシュボード (CQD) でテナントのアップロードとデータの作成に使用できる建物マップを作成する方法について学習します。
ms.openlocfilehash: 890e5e9b394cf8b600e635014c90ebb9053a1e07
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584036"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>通話品質ダッシュボード (CQD) の建物マップを作成する

Microsoft Teamsまたは Skype for Business Online のデプロイでは、すべてのクライアントが外部です。 その結果、既定では、クライアントが社内ネットワークに接続されているかどうかに関係なく、すべてのクライアントが通話品質ダッシュボード (CQD) で外部として報告されます。

CQD を使用する場合は、エンドポイントの場所と、エンドポイントが管理できるネットワークに接続されたのか、管理できないネットワークに接続されたのかを把握する必要があります。これは、管理できるネットワークのみを改善できるという前提です。 サブネットをアップロードし、CQD に情報を構築することで、CQD を有効にして、エンドポイントが内部 (管理された) ネットワークに接続されたのか、外部 (管理されていない) ネットワークに接続されたのかを判断できます。 このため、組織の建物マップを作成し [、CQD にアップロードすることが重要です](CQD-upload-tenant-building-data.md)。

## <a name="building-mapping-tools"></a>マッピング ツールの構築

組織のサブネットをマップする方法は多数あります。 ヘルプが必要な場合は、このブログ投稿で説明されている CQDTools PowerShell モジュール [を使用できます](https://aka.ms/cqdtools)。 これらのツールは PowerShell に基づいており、Active Directory (AD) のサイトとサービスと Microsoft DHCP サービスを使用して、建物のファイルを事前に設定するのに役立ちます。 これらのツールは、次のタスクに役立ちます。

1. サイトADサービスにクエリを実行し、に含まれる情報に基づいて建物ファイルを作成します。
1. Microsoft DHCP サーバーまたはサーバーにクエリを実行してサブネット情報を取得し、建物ファイルを自動的に作成します。
1. 既存の建物ファイルを検証し、重複と重複をチェックします。
1. CQD で、未作成のサブネットを検索します。

## <a name="related-topics"></a>関連トピック

[アップロードを作成し、CQD でデータを構築する](CQD-upload-tenant-building-data.md)