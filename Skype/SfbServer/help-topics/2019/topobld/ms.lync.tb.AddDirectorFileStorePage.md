---
title: ディレクター ファイル ストアの追加
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
ROBOTS: NOINDEX, NOFOLLOW
description: ディレクターのファイル ストアとして使用するファイル共有を指定する必要があります。 既存のファイル共有をファイル ストアに使用するか、ファイル共有を格納するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定できます。
ms.openlocfilehash: f134d561a948dbdb89ce655d59e5d5fc205bcbf4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811887"
---
# <a name="add-director-file-store"></a>ディレクター ファイル ストアの追加

ディレクターのファイル ストアとして使用するファイル共有を指定する必要があります。 既存のファイル共有をファイル ストアに使用するか、ファイル共有を格納するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定できます。

> [!IMPORTANT]
> トポロジにディレクターを追加する場合、トポロジの公開には、ファイル共有を設定し、ファイル ストアに使用するファイル共有に随意アクセス制御リスト (DACL) を構成するための適切なアクセスが必要になります。これには、トポロジ ビルダーを実行して新しいトポロジを公開するときに、ファイル共有のフル コントロール アクセス許可 (読み取り/書き込み/変更) を持つアカウントでログオンする必要があります。

ファイル共有の記憶域のサポートの詳細については、「[](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx)サポート」のドキュメントの「ファイル 記憶域のサポート」と「展開」のドキュメントの「SQL Server [Data and Log File Placement」](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)を参照してください。 ファイル共有の併置の詳細については、「サポート」のドキュメントの「[サポートされるサーバーの併置](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)」を参照してください。 ディレクターのトポロジ設計の詳細については、「展開」のドキュメントの [「Define a Single Director in Topology Builder」](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) を参照してください。


