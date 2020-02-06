---
title: アーカイブ サーバーのファイル ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: db55b6fd1a5b727e685a9b528c457e244a723c97
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794866"
---
# <a name="add-archiving-server-file-store"></a>アーカイブ サーバーのファイル ストアの追加

インスタント メッセージ (IM) と Web 会議 (ミーティング) の両方のコンテンツのアーカイブを有効にするには、すべての Web 会議のコンテンツのコピー用のファイル ストアとして使用するファイル共有を指定する必要があります。アーカイブ ファイル ストアとして既存のファイル共有を使用することも、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定することによって新しいファイル共有を指定することもできます。

> [!IMPORTANT]
> ファイル共有は、ファイル共有を作成する前にトポロジ ビルダーで定義できますが、トポロジを公開する前に定義済みの場所に作成しておく必要があります。 >、トポロジにアーカイブサーバーを追加するときに、トポロジビルダーでアーカイブファイルストアをセットアップし、ファイル共有に対して随意アクセス制御リスト (Dacl) を設定できるようにする必要があります。 そのため、トポロジ ビルダーを実行して新しいトポロジを公開するときに、サイト共有のフル コントロール アクセス許可 (読み取り/書き込み/変更) を持つアカウントでログインする必要があります。

ファイル共有の記憶域サポートの詳細については、「サポート」のドキュメントの「[File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx)」および「展開」のドキュメントの「[SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)」を参照してください。ファイル共有の併置の詳細については、「サポート」のドキュメントの「[Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)」を参照してください。


