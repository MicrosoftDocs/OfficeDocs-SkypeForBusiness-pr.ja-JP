---
title: 通話品質ダッシュボード (CQD) 用の建物マップを作成する
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
description: 通話品質ダッシュボード (CQD) でテナントと建物のデータをアップロードするために使用できる構築マップを作成する方法について説明します。
ms.openlocfilehash: 890e5e9b394cf8b600e635014c90ebb9053a1e07
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584036"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>通話品質ダッシュボード (CQD) 用の建物マップを作成する

Microsoft Teams または Skype for Business Online の展開では、すべてのクライアントが外部になります。 この結果、既定では、クライアントが社内の企業ネットワークに接続されているかどうかに関係なく、すべてのクライアントが通話品質ダッシュボード (CQD) の外部として報告されます。

CQD を使用する場合は、エンドポイントの場所と、管理できないネットワークに接続されていたかどうかを把握しておく必要があります。そのためには、管理可能なネットワークのみを対象としていることを前提としています。 サブネットと建物の情報を CQD にアップロードすることによって、CQD は、エンドポイントが内部 (管理された) ネットワークに接続されているのか、外部の (管理されている) ネットワークに接続されているのかを確認できます。 そのため、組織の構築地図を作成し、 [CQD にアップロード](CQD-upload-tenant-building-data.md)することが重要です。

## <a name="building-mapping-tools"></a>作成マッピングツール

組織のサブネットをマッピングするには、さまざまな方法があります。 ヘルプが必要な場合は、この[ブログ投稿](https://aka.ms/cqdtools)で説明されている CQDTools PowerShell モジュールを使用することができます。 これらのツールは、PowerShell に基づいており、Active Directory (AD) のサイトとサービス、および Microsoft DHCP サービスを使用して、作成したファイルを事前に作成するのに役立ちます。 これらのツールは、次のタスクを実行するときに役立ちます。

1. 広告サイトとサービスを照会し、その中に含まれている情報に基づいて建物ファイルを作成します。
1. Microsoft DHCP サーバーまたはサーバーに照会して、サブネット情報を取得し、建物ファイルを自動的に作成します。
1. 重複しているかどうかを確認し、既存の建物ファイルを検証します。
1. CQD でマッピングされていないサブネットを検索します。

## <a name="related-topics"></a>関連トピック

[CQD でテナントと建物データをアップロードする](CQD-upload-tenant-building-data.md)