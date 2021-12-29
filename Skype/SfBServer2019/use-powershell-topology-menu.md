---
title: トポロジ メニューのタスクに PowerShell を使用する
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: '概要: Skype for Business Serverトポロジ メニューのコマンドレット マッピングに移動します。'
ms.openlocfilehash: da5374863d7b9e7c8217802ce98e10cfdab92e54
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626228"
---
# <a name="topology"></a>トポロジ

この記事では、従来のコントロール パネルの **トポロジ** メニュー項目と同様の結果をコマンドレットを使用してどのように実現できるのかについて説明します。

この記事では、次のサブメニューについて説明します。

- [トポロジ](#topology)
  - [状態](#status)
  - [サーバー アプリケーション](#server-application)
  - [簡易 URL](#simple-url)
  - [信頼済みアプリケーション](#trusted-application)

## <a name="status"></a>状態

**STATUS** サブメニューを使用すると、管理者はトポロジ内のコンピューターを管理できます。

STATUS でユーザーが実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessコマンドレットについて検討します。

---

> **シナリオ 1**: すべてのコンピューターとその状態を一覧表示する

   ![コンピューターと状態の一覧表示](./media/topology-status-1.png)

   ***コマンドレット***

   [Get-CsPool](/powershell/module/skype/get-cspool)

   ***例***

   ```powershell
    Get-CsPool
   ```

   ***コマンドレット***

   [Get-CsComputer](/powershell/module/skype/get-cscomputer)

   ***例***

   ```powershell
    Get-CsComputer
   ```

   ***コマンドレット***

   [Get-CsManagementStoreReplicationStatus](/powershell/module/skype/get-csmanagementstorereplicationstatus)

   ***例***

   ```powershell
   Get-CsManagementStoreReplicationStatus
   ```

---

## <a name="server-application"></a>サーバー アプリケーション

サーバー アプリケーションは、サーバー アプリケーションの下で実行される個々のSkype for Business Server。 **SERVER APPLICATION** サブメニューは、管理者がアプリケーションの一部として実行されているアプリケーション (またはすべて) に関する情報をSkype for Business Server。

SERVER **APPLICATION** でユーザーが実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessコマンドレットについて検討します。

---
> **シナリオ 1**: すべてのサーバー アプリケーションを一覧表示する

   ![サーバー アプリケーションの一覧](./media/server-application-1.png)

***コマンドレット***

[Get-CsServerApplication](/powershell/module/skype/get-csserverapplication)

***例***

```powershell
 Get-CsServerApplication
```

---

> **シナリオ 2:** サーバー アプリケーションの重大な/非選択を有効/無効または選択する

   ![サーバー アプリケーションの編集](./media/server-application-2.png)

***コマンドレット***

[Set-CsServerApplication](/powershell/module/skype/get-csserverapplication)

***例***

```powershell
 Set-CsServerApplication -Identity "Registrar:atl-cs-001.litwareinc.com/ExumRouting" -Enabled $True
```

---

## <a name="simple-url"></a>簡易 URL

単純な URL を使用すると、ユーザーは会議や会議に簡単に参加できます。また、管理者が Skype for Business Server コントロール パネルにログオンしやすくなっています。SIMPLE **URL** サブメニューを使用すると、管理者が会議や会議を表示できます。

単純な **URL** でユーザーが実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessコマンドレットについて検討します。

---
> **シナリオ 1**: すべての簡易 URL 構成を一覧表示する

   ![簡易 URL の一覧](./media/simple-url-1.png)

***コマンドレット***

[Get-CsSimpleUrlConfiguration](/powershell/module/skype/get-cssimpleurlconfiguration)

***例***

```powershell
 Get-CsSimpleUrlConfiguration | Select-Object -ExpandProperty SimpleUrl
```

---

## <a name="trusted-application"></a>信頼済みアプリケーション

信頼済みアプリケーションは、Skype for Business Server の一部として実行する信頼できる状態が与えられたが、製品の組み込み部分ではない、サード パーティによって開発されたアプリケーションです。TRUSTED **APPLICATION サブメニュー** は、管理者がそれらを表示するのに役立ちます。

TRUSTED **APPLICATION** でユーザーが実行できるさまざまなタスクと、それらのタスクがマップされるSkype for Businessコマンドレットについて考えさせてください。

---
> **シナリオ 1**: 信頼できるアプリケーションの一覧を表示する

   ![信頼済みアプリケーションの一覧](./media/trusted-application-1.png)

***コマンドレット***

[Get-CsTrustedApplication](/powershell/module/skype/get-cstrustedapplication)

***例***

```powershell
 Get-CsTrustedApplication
```

---
