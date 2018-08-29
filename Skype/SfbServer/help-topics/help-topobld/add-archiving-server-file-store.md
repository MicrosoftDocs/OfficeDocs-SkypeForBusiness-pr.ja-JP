---
title: アーカイブ サーバーのファイル ストアの追加
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: インスタント メッセージ (IM) と Web 会議 (ミーティング) の両方のコンテンツのアーカイブを有効にするには、すべての Web 会議のコンテンツのコピー用のファイル ストアとして使用するファイル共有を指定する必要があります。アーカイブ ファイル ストアとして既存のファイル共有を使用することも、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定することによって新しいファイル共有を指定することもできます。
ms.openlocfilehash: 9d32871fbfdd60f3c417be3d6f60a06192474df1
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23260546"
---
# <a name="add-archiving-server-file-store"></a>アーカイブ サーバーのファイル ストアの追加

インスタント メッセージ (IM) と Web 会議 (ミーティング) の両方のコンテンツのアーカイブを有効にするには、すべての Web 会議のコンテンツのコピー用のファイル ストアとして使用するファイル共有を指定する必要があります。アーカイブ ファイル ストアとして既存のファイル共有を使用することも、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定することによって新しいファイル共有を指定することもできます。

> [!IMPORTANT]
> ファイル共有は、ファイル共有を作成する前にトポロジ ビルダーで定義できますが、トポロジを公開する前に定義済みの場所に作成しておく必要があります。 > アーカイブ サーバーをトポロジに追加すると、トポロジ ビルダーできる必要があります、アーカイブ ファイル ストアを設定し、ファイル ストアに使用するファイル共有の随意アクセス制御リスト (Dacl) を構成します。 そのため、トポロジ ビルダーを実行して新しいトポロジを公開するときに、サイト共有のフル コントロール アクセス許可 (読み取り/書き込み/変更) を持つアカウントでログインする必要があります。

ファイル共有のストレージ ・ サポートの詳細についてを参照してください[ファイル記憶域をサポート](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx)サポート マニュアルと[SQL Server のデータとログ ファイルの配置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)の展開に関するドキュメント。 コロケーション ファイル共有の詳細については、サポート ドキュメントで[サポートされているサーバーのコロケーション](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)を参照してください。


