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
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
ROBOTS: NOINDEX, NOFOLLOW
description: データベースファイルとログ ファイルをサーバーに配置するための詳細オプションをSQL Server。 使用できるオプションは次のとおりです。
ms.openlocfilehash: 5da2d50bf6571408f63403998443155307d86e2b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805737"
---
# <a name="install-database-options-page"></a>データベースのインストール オプション ページ

データベースファイルとログ ファイルをサーバーに配置するための詳細オプションをSQL Server。 使用できるオプションは次のとおりです。

> [!IMPORTANT]
> ユーザーのコンピューターでのデータとログ ファイルの配置に関する要件とポリシーに最適なオプションSQL Serverします。

 **データベース ファイルの場所を** 自動的に決定する : 既定のオプションでは、SQL Server で使用可能な領域を決定し、最適なパフォーマンスを得るデータベースとログ ファイルを配布するアルゴリズムが使用されます。

 **インスタンスSQL Server既定値を使用** する : このオプションを選択すると、データベース のインスタンス設定に基づいてデータベース ファイルとログ ファイルSQL Server。 通常、これらのオプションの管理と構成はデータベース管理者が行います。

 **ターゲット SQL Server** でのこれらのパス: データベースとログ ファイルが配置されるドライブとフォルダーへの完全なパスを入力して、SQL Server データベースとログ ファイルの独自のパスを定義するには、このオプションを選択します。

> [!IMPORTANT]
> 入力したパスは、パフォーマンス最適化アルゴリズムに基づいて変更されることがあります。 詳細については、「[Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)」を参照してください。

 [**OK**]: 変更を確定するには、[OK] をクリックします。

 [**キャンセル**]: 変更を破棄して [データベースのインストール] 画面に戻るには、[キャンセル] をクリックします。

 [**ヘルプ**]: このヘルプ ページにアクセスするには、[ヘルプ] をクリックします。

## <a name="see-also"></a>関連項目

[SQL Server データとログ ファイルの配置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
