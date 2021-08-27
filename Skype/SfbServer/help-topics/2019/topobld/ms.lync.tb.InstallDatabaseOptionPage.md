---
title: データベースのインストール オプション ページ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
ROBOTS: NOINDEX, NOFOLLOW
description: データベース ファイルとログ ファイルをサーバーに配置するための高度なオプションを構成SQL Server。 使用できるオプションは次のとおりです。
ms.openlocfilehash: 7a082bcace083a1b53ea5b94953a38364feb197a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611000"
---
# <a name="install-database-options-page"></a>データベースのインストール オプション ページ

データベース ファイルとログ ファイルをサーバーに配置するための高度なオプションを構成SQL Server。 使用できるオプションは次のとおりです。

> [!IMPORTANT]
> コンピューター上のデータとログ ファイルの配置に関連する要件とポリシーに最適なオプションSQL Serverします。

 **データベース ファイルの場所を** 自動的に決定する: 既定のオプションは、SQL Server で使用可能な領域を決定し、最適なパフォーマンスを得るデータベース ファイルとログ ファイルを配布するアルゴリズムを使用します。

 **[SQL Server既定値を使用** する: データベース ファイルとログ ファイルをインスタンス設定に基づいてデータベース ファイルを配置するには、このオプションをSQL Server。 通常、これらのオプションの管理と構成はデータベース管理者が行います。

 **ターゲット** SQL Server でのこれらのパス: このオプションを選択して、SQL Server データベースとログ ファイルの独自のパスを定義するには、データベースファイルとログ ファイルが配置されるドライブとフォルダーへの完全なパスを入力します。

> [!IMPORTANT]
> 入力したパスは、パフォーマンス最適化アルゴリズムに基づいて変更されることがあります。詳細については、「[Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)」を参照してください。

 [**OK**]: 変更を確定するには、[OK] をクリックします。

 [**キャンセル**]: 変更を破棄して [データベースのインストール] 画面に戻るには、[キャンセル] をクリックします。

 [**ヘルプ**]: このヘルプ ページにアクセスするには、[ヘルプ] をクリックします。

## <a name="see-also"></a>関連項目

[SQL Server データとログ ファイルの配置](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)