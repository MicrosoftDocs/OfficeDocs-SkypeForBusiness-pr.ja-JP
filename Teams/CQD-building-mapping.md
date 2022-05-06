---
title: 通話品質ダッシュボード (CQD) のビルド マップを作成する
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 通話品質ダッシュボード (CQD) でテナントのアップロードとデータの構築に使用できる建物マップを作成する方法について説明します。
ms.openlocfilehash: a119324090d05b593eb1ed66f41efbb7a5bd7a0a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58634101"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>通話品質ダッシュボード (CQD) のビルド マップを作成する

Microsoft TeamsまたはSkype for Business Online 展開では、すべてのクライアントが外部です。 その結果、既定では、クライアントが内部企業ネットワークに接続されているかどうかに関係なく、すべてのクライアントが通話品質ダッシュボード (CQD) の外部として報告されます。

CQD を使用する場合は、エンドポイントの場所と、エンドポイントが管理できるネットワークに接続されていたか、管理できないネットワークに接続されていたかを知る必要があります。これは、管理できるネットワークのみを改善できるということです。 サブネットをアップロードして CQD に情報を構築することで、CQD を有効にして、エンドポイントが内部 (マネージド) ネットワークに接続されていたか、外部 (非管理対象) ネットワークに接続されていたかを判断できます。 そのため、組織のビルド マップを作成し、 [CQD にアップロードすることが](CQD-upload-tenant-building-data.md)重要です。

## <a name="building-mapping-tools"></a>マッピング ツールの構築

組織のサブネットをマップするには、さまざまな方法があります。 ヘルプが必要な場合は、この [ブログ投稿](https://aka.ms/cqdtools)で説明されている CQDTools PowerShell モジュールを使用できます。 これらのツールは PowerShell に基づいており、Active Directory (AD) のサイトとサービスと Microsoft DHCP サービスを使用して、ビルド ファイルを事前設定するのに役立ちます。 これらのツールは、次のタスクに役立ちます。

1. AD サイトとサービスにクエリを実行し、その中に含まれる情報に基づいてビルド ファイルを作成します。
1. Microsoft DHCP サーバーまたはサーバーにクエリを実行してサブネット情報をプルし、ビルド ファイルを自動的に作成します。
1. 既存のビルド ファイルを検証し、重複と重複を確認します。
1. CQD でマップされていないサブネットを検索します。

## <a name="related-topics"></a>関連項目

[CQD でのテナントとデータの構築をアップロードする](CQD-upload-tenant-building-data.md)