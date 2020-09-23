---
title: データベースのインストールと作成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: 展開用に作成するデータベースを選択します。 既定では、定義済みのサイトに定義された SQL Server 上にデータベースが作成され、データベースを配置している SQL Server に基づいてデータベースファイルが自動的に展開および構成されます。
ms.openlocfilehash: ade264fcda73df408f6bb323dd1e3733ccdd45f1
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215388"
---
# <a name="install-and-create-databases"></a>データベースのインストールと作成

展開用に作成するデータベースを選択します。 既定では、定義済みのサイトに定義された SQL Server 上にデータベースが作成され、データベースを配置している SQL Server に基づいてデータベースファイルが自動的に展開および構成されます。

 [**作成するデータベースを選択**]: 展開および構成を行う任意のデータベースのチェックボックスをオンにします。展開を行う一部または全部のデータベースのチェック ボックスをオンにします。

> [!CAUTION]
> SQL Server は、インスタンスに対して既に構成されている必要があります (存在する場合)。また、データベースの展開先のインスタンスが収まるようにファイアウォールポートを開く必要があります。 詳細については、「 [Lync server 2013 プレビュー用の SQL Server を構成する](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)」を参照してください。

 **詳細**: sql server をクリックし、[ **詳細設定** ] ボタンをクリックして、sql server 上のデータベースファイルの場所のオプションを選択します。 高度なデータベース ファイル配置の詳細については、「[Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)」を参照してください。

 [**戻る**]: このボタンをクリックすると、前画面に戻ります (このダイアログへの到達方法によっては、必ずしも利用できない場合があります)。

 [**次へ**]: このボタンをクリックすると、現在のダイアログでの選択を確定し、追加情報を構成する次のダイアログに移動します。

 [**キャンセル**]: このボタンをクリックすると、構成を終了し、変更を破棄します。 終了し、変更を破棄する場合、確認メッセージが表示されることがあります (すべての構成画面で表示されるわけではありません)。 **[はい]** を選択すると、現在の構成が閉じられ、現在の構成が閉じて、トポロジビルダーに戻ります。 [**いいえ**] を選択すると、現在の構成ダイアログに戻り、構成を続行できます。

 [**ヘルプ**]: [**ヘルプ**] をクリックすると、現在の構成ダイアログに関連付けられた、このヘルプ情報を表示します。


