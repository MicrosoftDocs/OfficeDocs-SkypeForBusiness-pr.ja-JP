---
title: フロント エンド ファイル ストアの追加
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
description: サーバーまたはフロントエンド プールのファイル ストアとして使用するファイル共有Standard Edition指定Enterprise Edition必要があります。 ファイル ストアに既存のファイル共有を使用するか、ファイル共有を保存するファイル サーバーの完全修飾ドメイン名 (FQDN) と、新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定できます。
ms.openlocfilehash: 85e1e68c64e8175968211cccac83bcf6302cb5e0
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844550"
---
# <a name="add-front-end-file-store"></a>フロント エンド ファイル ストアの追加

サーバーまたはフロントエンド プールのファイル ストアとして使用するファイル共有Standard Edition指定Enterprise Edition必要があります。 ファイル ストアに既存のファイル共有を使用するか、ファイル共有を保存するファイル サーバーの完全修飾ドメイン名 (FQDN) と、新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定できます。

> [!IMPORTANT]
> ファイル共有は、フロントエンド サーバー上Enterprise Editionすることはできませんが、サーバー上にStandard Editionできます。

> [!IMPORTANT]
> ファイル共有を作成する前にトポロジ ビルダーでファイル共有を定義できますが、トポロジを公開する前に定義する定義済みの場所にファイル共有を作成する必要があります。

> [!IMPORTANT]
> トポロジに Enterprise フロント エンドのプールまたは Standard Edition サーバーを追加する場合、トポロジ ビルダーでファイル共有を設定し、ファイル ストアに使用するファイル共有に随意アクセス制御リスト (DACL) を構成できる必要があります。これには、トポロジ ビルダーを実行して新しいトポロジを公開するときに、サイト共有のフル コントロール アクセス許可 (読み取り/書き込み/変更) を持つアカウントでログインする必要があります。

ファイル共有の記憶域のサポートの詳細については、「サポート」のドキュメントの「file [Storage](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support)サポート」と「展開」のドキュメントの「SQL Server[データ](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)とログ ファイルの配置」を参照してください。 ファイル共有の併置の詳細については、「サポート」のドキュメントの「[サポートされるサーバーの併置](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)」を参照してください。 Enterprise Edition フロント エンドのプールのトポロジ設計の詳細については、「展開」のドキュメントの「[Define and Configure a Front End Pool (フロント エンドのプールの定義と構成)](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)」を参照してください。