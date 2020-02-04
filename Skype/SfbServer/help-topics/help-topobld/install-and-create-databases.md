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
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: 展開用に作成するデータベースを選択します。 既定では、データベースは定義されたサイト内の定義された SQL Server 上に作成され、データベースの配置元の SQL Server に基づいて自動的にデータベースファイルを展開し、構成します。
ms.openlocfilehash: cf3493932fc699751cb31e1ab6f76312195b4e0a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697212"
---
# <a name="install-and-create-databases"></a>データベースのインストールと作成

展開用に作成するデータベースを選択します。 既定では、データベースは定義されたサイト内の定義された SQL Server 上に作成され、データベースの配置元の SQL Server に基づいて自動的にデータベースファイルを展開し、構成します。

 **作成するデータベースを選択**します。展開して構成するデータベースのチェックボックスをオンにします。 展開する任意またはすべてのデータベースのチェックボックスをオンにします。

> [!CAUTION]
> SQL Server はインスタンス (存在する場合) に対して既に設定されている必要があります。また、データベースの展開先のインスタンスに対応するためにファイアウォールポートを開く必要があります。 詳細については、「 [Lync server 2013 用に SQL server を構成する](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)」を参照してください。

 **詳細設定**: sql server をクリックし、[**詳細設定**] ボタンをクリックして、sql server 上のデータベースファイルの場所のオプションを選択します。 データベースファイルの高度な配置について詳しくは、「 [Lync Server 管理シェルを使用したデータベースのインストール](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)」をご覧ください。

 **戻る**: このボタンをクリックすると、前の画面に戻ります (このダイアログでの表示に応じて、常に使用できるとは限りません)。

 **次へ**: このボタンをクリックすると、現在のダイアログで選択した内容がコミットされ、追加情報を構成するための次のダイアログボックスが表示されます。

 **[キャンセル**]: このボタンをクリックすると、構成が終了し、変更内容は破棄されます。 一部の構成画面では、変更を終了して破棄するかどうかを確認するメッセージが表示される場合があります。 **[はい]** を選択すると、現在の構成が閉じられ、現在の構成が閉じて、トポロジビルダーに戻ります。 [**いいえ**] を選択すると、現在の構成ダイアログに戻り、構成を続行することができます。

 **ヘルプ**: [**ヘルプ**] ボタンをクリックすると、現在の構成ダイアログに関連付けられたこのヘルプ情報が表示されます。


