---
title: ディレクター ファイル ストアの追加
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
description: ディレクターのファイル ストアとして使用するファイル共有を指定する必要があります。 ファイル ストアに既存のファイル共有を使用するか、ファイル共有を保存するファイル サーバーの完全修飾ドメイン名 (FQDN) と、新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定できます。
ms.openlocfilehash: c62a929efe6601f1a9705060bd456c43034d77ff
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390359"
---
# <a name="add-director-file-store"></a>ディレクター ファイル ストアの追加

ディレクターのファイル ストアとして使用するファイル共有を指定する必要があります。 ファイル ストアに既存のファイル共有を使用するか、ファイル共有を保存するファイル サーバーの完全修飾ドメイン名 (FQDN) と、新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定できます。

> [!IMPORTANT]
> トポロジにディレクターを追加する場合、トポロジの公開には、ファイル共有を設定し、ファイル ストアに使用するファイル共有に随意アクセス制御リスト (DACL) を構成するための適切なアクセスが必要になります。これには、トポロジ ビルダーを実行して新しいトポロジを公開するときに、ファイル共有のフル コントロール アクセス許可 (読み取り/書き込み/変更) を持つアカウントでログオンする必要があります。

ファイル共有の記憶域のサポートの詳細については、「サポート」のドキュメントの「File [Storage](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) サポート」と「展開」のドキュメントの「SQL Server [データ](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)とログ ファイルの配置」を参照してください。 ファイル共有の併置の詳細については、「サポート」のドキュメントの「[サポートされるサーバーの併置](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)」を参照してください。 ディレクターのトポロジの設計の詳細については、「展開」のドキュメントの「 [Define a Single Director in Topology Builder](/previous-versions/office/lync-server-2013/lync-server-2013-define-optional-director-topologies-in-your-topology) 」を参照してください。