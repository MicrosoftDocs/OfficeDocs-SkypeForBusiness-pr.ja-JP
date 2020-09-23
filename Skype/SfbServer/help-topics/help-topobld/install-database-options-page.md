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
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: SQL Server でデータベースとログファイルを配置するための詳細オプションを構成します。 使用できるオプションは次のとおりです。
ms.openlocfilehash: 4c8c456aa1fd0e9eee150e184b4d1f7934c26b65
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215308"
---
# <a name="install-database-options-page"></a>データベースのインストール オプション ページ

SQL Server でデータベースとログファイルを配置するための詳細オプションを構成します。 使用できるオプションは次のとおりです。

> [!IMPORTANT]
> SQL Server コンピューターでのデータおよびログファイルの配置に関する要件とポリシーに最適なオプションを選択します。

 [**データベースファイルの場所を自動的に決定**する]: 既定のオプションでは、SQL Server で使用可能な領域を決定するアルゴリズムを使用し、データベースおよびログファイルを配布して最適なパフォーマンスを実現します。

 [ **Sql server インスタンスの既定値を使用**する]: このオプションを選択すると、sql server のインスタンス設定に基づいてデータベースファイルとログファイルが配置されます。 通常、これらのオプションの管理と構成はデータベース管理者が行います。

 **[ターゲット SQL server のパス**]: このオプションを選択すると、データベースとログファイルを配置するドライブとフォルダーへの完全なパスを入力することによって、sql server データベースとログファイルのパスを定義することができます。

> [!IMPORTANT]
> 入力したパスは、パフォーマンス最適化アルゴリズムに基づいて変更されることがあります。 詳細については、「[Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)」を参照してください。

 [**OK**]: 変更を確定するには、[OK] をクリックします。

 [**キャンセル**]: 変更を破棄して [データベースのインストール] 画面に戻るには、[キャンセル] をクリックします。

 [**ヘルプ**]: このヘルプ ページにアクセスするには、[ヘルプ] をクリックします。

## <a name="see-also"></a>関連項目

[SQL Server データとログ ファイルの配置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
