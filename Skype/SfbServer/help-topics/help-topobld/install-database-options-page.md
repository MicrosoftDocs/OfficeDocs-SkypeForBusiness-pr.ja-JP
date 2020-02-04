---
title: データベースのインストール オプション ページ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: SQL Server でデータベースファイルとログファイルの配置の詳細オプションを構成します。 利用可能なオプションは次のとおりです。
ms.openlocfilehash: 0abcf0be4c6e7a4d808a7abaaad713c1b35cd37e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697202"
---
# <a name="install-database-options-page"></a>データベースのインストール オプション ページ

SQL Server でデータベースファイルとログファイルの配置の詳細オプションを構成します。 利用可能なオプションは次のとおりです。

> [!IMPORTANT]
> SQL Server コンピューターのデータとログファイルの配置に関する要件とポリシーに最も適合するオプションを選択します。

 [**データベースファイルの場所を自動的に特定**する]: 既定のオプションでは、SQL Server の空き領域を決定するアルゴリズムが使用され、最適なパフォーマンスを実現するためにデータベースとログファイルが配布されます。

 [ **Sql server インスタンスの既定値を使用**する]: このチェックボックスをオンにすると、sql server のインスタンスの設定に基づいてデータベースファイルとログファイルが配置されます。 これらのオプションは、通常、データベース管理者によって管理および構成されます。

 **[ターゲット SQL server 上のパス**]: このオプションを選択すると、sql server データベースおよびログファイルを保存するドライブとフォルダーへのフルパスを入力して、sql server データベースとログファイルに独自のパスを定義できます。

> [!IMPORTANT]
> 入力したパスは、インストールのパフォーマンス最適化アルゴリズムに基づいて変更される可能性があります。 詳細については、「 [Lync Server 管理シェルを使用したデータベースのインストール](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)」を参照してください。

 [ **Ok**] をクリックして変更をコミットします。

 [**キャンセル**]: 変更を破棄して [データベースのインストール] 画面に戻るには、[キャンセル] をクリックします。

 **ヘルプ**: このヘルプページにアクセスするには、[ヘルプ] をクリックします。

## <a name="see-also"></a>関連項目

[SQL Server データとログファイルの配置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
