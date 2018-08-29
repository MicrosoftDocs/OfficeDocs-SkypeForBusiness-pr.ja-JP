---
title: ディレクターのファイル ストアの追加
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
ROBOTS: NOINDEX, NOFOLLOW
description: ディレクターのファイル ストアとして使用するファイル共有を指定する必要があります。既存のファイル共有をファイル ストアに使用できます。または、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。
ms.openlocfilehash: 76968644617b6ec9e8fe255c0aae93ee07eaa207
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23245070"
---
# <a name="add-director-file-store"></a>ディレクターのファイル ストアの追加

ディレクターのファイル ストアとして使用するファイル共有を指定する必要があります。既存のファイル共有をファイル ストアに使用できます。または、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。

> [!IMPORTANT]
> トポロジにディレクターを追加する場合、トポロジの公開には、ファイル共有を設定し、ファイル ストアに使用するファイル共有に随意アクセス制御リスト (DACL) を構成するための適切なアクセス権が必要になります。そのため、トポロジ ビルダーを実行して新しいトポロジを公開するときに、ファイル共有のフル コントロール アクセス許可 (読み取り/書き込み/変更) を持つアカウントでログオンする必要があります。

ファイル共有のストレージ ・ サポートの詳細についてを参照してください[ファイル記憶域をサポート](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx)サポート マニュアルと[SQL Server のデータとログ ファイルの配置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)の展開に関するドキュメント。 コロケーション ファイル共有の詳細については、サポート ドキュメントで[サポートされているサーバーのコロケーション](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)を参照してください。 ディレクターのトポロジの設計についての詳細は、展開に関するドキュメントで[定義するトポロジ ビルダーで単一のディレクター](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx)を参照してください。


