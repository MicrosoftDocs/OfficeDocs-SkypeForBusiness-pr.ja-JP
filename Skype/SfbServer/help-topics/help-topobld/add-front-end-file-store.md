---
title: フロントエンド ファイル ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
description: Standard Edition サーバーまたは Enterprise Edition フロントエンド プールのファイル ストアとして使用するファイル共有を指定する必要があります。既存のファイル共有をファイル ストアに使用できます。または、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。
ms.openlocfilehash: 7fa67050e93adb9909c6a124b0b64e7510f1c531
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303691"
---
# <a name="add-front-end-file-store"></a>フロントエンド ファイル ストアの追加

Standard Edition サーバーまたは Enterprise Edition フロントエンド プールのファイル ストアとして使用するファイル共有を指定する必要があります。既存のファイル共有をファイル ストアに使用できます。または、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。

> [!IMPORTANT]
> ファイル共有は、Enterprise Edition フロントエンド サーバーに配置することはできませんが、Standard Edition サーバーに配置することができます。

> [!IMPORTANT]
> ファイル共有を作成する前にトポロジ ビルダーでファイル共有を定義できますが、トポロジを公開する前に定義する定義済みの場所にファイル共有を作成する必要があります。

> [!IMPORTANT]
> トポロジに Enterprise フロントエンドのプールまたは Standard Edition サーバーを追加する場合、トポロジ ビルダーでファイル共有を設定し、ファイル ストアに使用するファイル共有に随意アクセス制御リスト (DACL) を構成できる必要があります。これには、トポロジ ビルダーを実行して新しいトポロジを公開するときに、サイト共有のフル コントロール アクセス許可 (読み取り/書き込み/変更) を持つアカウントでログインする必要があります。

ファイル共有の記憶域サポートの詳細については、「サポート」のドキュメントの「[File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx)」、および「展開」のドキュメントの「[SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)」を参照してください。ファイル共有の併置の詳細については、「サポート」のドキュメントの「[Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)」を参照してください。Enterprise Edition フロントエンド プールのトポロジ設計の詳細については、「展開」のドキュメントの「[Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)」を参照してください。


