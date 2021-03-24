---
title: データベースのインストールと作成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
ROBOTS: NOINDEX, NOFOLLOW
description: 展開用に作成するデータベースを選択します。 既定では、データベースは定義されたサイトの定義済みの SQL Server に作成され、データベースを配置する SQL Server に基づいてデータベース ファイルを自動的に展開および構成します。
ms.openlocfilehash: 160b42e510fc54b3f03375a0c86bc9f6bdf83f5f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100053"
---
# <a name="install-and-create-databases"></a>データベースのインストールと作成

展開用に作成するデータベースを選択します。 既定では、データベースは定義されたサイトの定義済みの SQL Server に作成され、データベースを配置する SQL Server に基づいてデータベース ファイルを自動的に展開および構成します。

 [**作成するデータベースを選択**]: 展開および構成を行う任意のデータベースのチェックボックスをオンにします。展開を行う一部または全部のデータベースのチェック ボックスをオンにします。

> [!CAUTION]
> データベースSQL Serverに対応するために、インスタンス用に構成されている必要があります (存在する場合)、ファイアウォール ポートを開いて、データベースを展開するインスタンスに合わせて開く必要があります。 詳細については、「Configure [SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)

 **Advanced**: [詳細] ボタンをSQL Serverし、[詳細設定] ボタンをクリックして、データベース 上のデータベース ファイルの場所のオプションを選択SQL Server。 高度なデータベース ファイル配置の詳細については、「[Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)」を参照してください。

 [**戻る**]: このボタンをクリックすると、前画面に戻ります (このダイアログへの到達方法によっては、必ずしも利用できない場合があります)。

 [**次へ**]: このボタンをクリックすると、現在のダイアログでの選択を確定し、追加情報を構成する次のダイアログに移動します。

 [**キャンセル**]: このボタンをクリックすると、構成を終了し、変更を破棄します。 終了し、変更を破棄する場合、確認メッセージが表示されることがあります (すべての構成画面で表示されるわけではありません)。 [はい **] を** 選択すると、現在の構成が閉じ、現在の構成が閉じ、トポロジ ビルダーに戻されます。 [**いいえ**] を選択すると、現在の構成ダイアログに戻り、構成を続行できます。

 [**ヘルプ**]: [**ヘルプ**] をクリックすると、現在の構成ダイアログに関連付けられた、このヘルプ情報を表示します。