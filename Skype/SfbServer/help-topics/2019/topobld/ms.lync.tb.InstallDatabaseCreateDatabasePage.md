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
description: 展開用に作成するデータベースを選択します。 既定では、データベースは定義済みのサイトの定義済みの SQL Server に作成され、データベースを配置する SQL Server に基づいてデータベース ファイルを自動的に展開および構成します。
ms.openlocfilehash: 4d7a6e4f67dd6b97c8f5f837589af7b096da50b5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835717"
---
# <a name="install-and-create-databases"></a>データベースのインストールと作成

展開用に作成するデータベースを選択します。 既定では、データベースは定義済みのサイトの定義済みの SQL Server に作成され、データベースを配置する SQL Server に基づいてデータベース ファイルを自動的に展開および構成します。

 [**作成するデータベースを選択**]: 展開および構成を行う任意のデータベースのチェックボックスをオンにします。展開を行う一部または全部のデータベースのチェック ボックスをオンにします。

> [!CAUTION]
> データベースSQL Serverインスタンス用に構成されている必要があります (存在する場合)、データベースを展開するインスタンスに合わせてファイアウォール ポートを開く必要があります。 詳細については、「Configure [SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)

 **[詳細設定**] : [SQL Server] をクリックし、[詳細設定] ボタンをクリックして、データベース上のデータベース ファイルの場所のオプションをSQL Server。 高度なデータベース ファイル配置の詳細については、「[Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)」を参照してください。

 [**戻る**]: このボタンをクリックすると、前画面に戻ります (このダイアログへの到達方法によっては、必ずしも利用できない場合があります)。

 [**次へ**]: このボタンをクリックすると、現在のダイアログでの選択を確定し、追加情報を構成する次のダイアログに移動します。

 [**キャンセル**]: このボタンをクリックすると、構成を終了し、変更を破棄します。 終了し、変更を破棄する場合、確認メッセージが表示されることがあります (すべての構成画面で表示されるわけではありません)。 [はい **] を** 選択すると、現在の構成が閉じ、現在の構成が閉じ、トポロジ ビルダーに戻されます。 [**いいえ**] を選択すると、現在の構成ダイアログに戻り、構成を続行できます。

 [**ヘルプ**]: [**ヘルプ**] をクリックすると、現在の構成ダイアログに関連付けられた、このヘルプ情報を表示します。


