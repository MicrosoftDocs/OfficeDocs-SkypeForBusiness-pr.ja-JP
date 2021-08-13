---
title: アーカイブ サーバーのファイル ストアを追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
ROBOTS: NOINDEX, NOFOLLOW
description: インスタント メッセージ (IM) と Web 会議 (ミーティング) の両方のコンテンツのアーカイブを有効にするには、すべての Web 会議のコンテンツのコピー用のファイル ストアとして使用するファイル共有を指定する必要があります。アーカイブ ファイル ストアとして既存のファイル共有を使用することも、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定することによって新しいファイル共有を指定することもできます。
ms.openlocfilehash: b3753970dbdcc6ac03edebef3ccb13d74fb86dc161e437bef9646486c6ac7f08
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322139"
---
# <a name="add-archiving-server-file-store"></a>アーカイブ サーバーのファイル ストアの追加

インスタント メッセージ (IM) と Web 会議 (ミーティング) の両方のコンテンツのアーカイブを有効にするには、すべての Web 会議のコンテンツのコピー用のファイル ストアとして使用するファイル共有を指定する必要があります。アーカイブ ファイル ストアとして既存のファイル共有を使用することも、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定することによって新しいファイル共有を指定することもできます。

> [!IMPORTANT]
> ファイル共有は、ファイル共有を作成する前にトポロジ ビルダーで定義できますが、トポロジを公開する前に定義済みの場所に作成しておく必要があります。 > トポロジにアーカイブ サーバーを追加する場合、トポロジ ビルダーは、アーカイブ ファイル ストアをセットアップし、ファイル ストアに使用するファイル共有の随意アクセス制御リスト (DACLs) を構成できる必要があります。 これには、トポロジ ビルダーを実行して新しいトポロジを公開するときに、サイト共有のフル コントロール アクセス許可 (読み取り/書き込み/変更) を持つアカウントでログインする必要があります。

ファイル共有の記憶域のサポートの詳細については、「サポート」のドキュメントの「file [Storage](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support)サポート」と「展開」のドキュメントの「SQL Server[データ](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)とログ ファイルの配置」を参照してください。 ファイル共有の併置の詳細については、「サポート」のドキュメントの「[Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)」を参照してください。