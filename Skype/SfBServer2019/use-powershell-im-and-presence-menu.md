---
title: IM とプレゼンス メニューのタスクに PowerShell を使用する
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
description: '概要: Skype for Business Server[IM とプレゼンス] メニューのコマンドレット マッピングに移動します。'
ms.openlocfilehash: 9d57e249fb839894454c05d25e78320153d4a306
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2021
ms.locfileid: "60888786"
---
# <a name="im-and-presence"></a>IM とプレゼンス

この記事では、従来のコントロール パネルの **IM and Presence** メニュー項目と同様の結果をコマンドレットを使用してどのように実現できるのかについて説明します。

この記事では、次のサブメニューについて説明します。

- [IM and Presence](#im-and-presence)
  - [ファイル フィルター](#file-filter)
  - [URL フィルター](#url-filter)

## <a name="file-filter"></a>ファイル フィルター

**FILE FILTER** サブメニューを使用すると、管理者は組織内のファイル転送フィルター構成を管理できます。 これらの構成は、ユーザーが特定の種類のファイル (.vbs または .ps1 ファイル拡張子を持つファイルなど) を Skype for Business Server クライアントを使用して転送する機能をブロックするために使用されます。

FILE **FILTER** でユーザーが実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessするコマンドレットについて説明します。

---

> **シナリオ 1**: すべてのファイル フィルターを一覧表示する

   ![リスト ファイル フィルター](./media/file-filter-1.png)

***コマンドレット***

[Get-CsFileTransferFilterConfiguration](/powershell/module/skype/get-csfiletransferfilterconfiguration)

***例***

```powershell
 Get-CsFileTransferFilterConfiguration
```

---

> **シナリオ 2:** 新しいファイル フィルターを作成する

   ![ファイル フィルターの作成](./media/file-filter-2.png)

***コマンドレット***

[New-CsFileTransferFilterConfiguration](/powershell/module/skype/new-csfiletransferfilterconfiguration)  

***例***

```powershell
 New-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **シナリオ 3:** 選択したファイル フィルターの詳細を取得する

   ![ファイル フィルターの取得](./media/file-filter-3.png)

***コマンドレット***

[Get-CsFileTransferFilterConfiguration](/powershell/module/skype/get-csfiletransferfilterconfiguration)

***例***

```powershell
 Get-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **シナリオ 4:** 選択したファイル フィルターを削除する

   ![ファイル フィルターの削除](./media/file-filter-4.png)

***コマンドレット***

[Remove-CsFileTransferFilterConfiguration](/powershell/module/skype/remove-csfiletransferfilterconfiguration)

***例***

```powershell
 Remove-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **シナリオ 5:** ファイル フィルターを更新する

   ![ファイル フィルターの更新](./media/file-filter-5.png)

***コマンドレット***

[Set-CsFileTransferFilterConfiguration](/powershell/module/skype/set-csfiletransferfilterconfiguration)

***例***

```powershell
 Set-CsFileTransferFilterConfiguration -Identity site:Redmond -Extensions @{Add=".ps1"}
```

---

## <a name="url-filter"></a>URL フィルター

IM と **プレゼンスの下** の **URL** FILTER サブメニュー項目を使用すると、管理者は URL フィルターを構成して、特定のプレフィックスを持つハイパーリンクがブロックまたはアクティブでなからなかっています。 (つまり、参加者はリンクをクリックして URI が参照するサイトに移動することはできません。リンクを手動でコピーしてブラウザーに貼り付ける必要があります)。

URL FILTER でユーザーが実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessするコマンドレットについて説明します。

---
> **シナリオ 1**: すべての Web URL フィルターを一覧表示する

   ![リスト URL フィルター](./media/url-filter-1.png)

***コマンドレット***

[Get-CsImFilterConfiguration](/powershell/module/skype/get-csimfilterconfiguration)

***例***

```powershell
 Get-CsImFilterConfiguration
```

---

> **シナリオ 2:** 新しい URL フィルターを作成する

   ![新しい URL フィルター](./media/url-filter-2.png)

***コマンドレット***

[New-CsImFilterConfiguration](/powershell/module/skype/new-csimfilterconfiguration)  

***例***

```powershell
 New-CsImFilterConfiguration -Identity site:Redmond
```

---

> **シナリオ 3:** 選択した URL フィルターの詳細を取得する

   ![URL フィルターの取得](./media/url-filter-3.png)

***コマンドレット***

[Get-CsImFilterConfiguration](/powershell/module/skype/get-csimfilterconfiguration)

***例***

```powershell
 Get-CsImFilterConfiguration -Identity site:Redmond
```

---

> **シナリオ 4:** 選択した URL フィルターを削除する

   ![URL フィルターの削除](./media/url-filter-4.png)

***コマンドレット***

[Remove-CsImFilterConfiguration](/powershell/module/skype/remove-csimfilterconfiguration)

***例***

```powershell
 Remove-CsImFilterConfiguration -Identity site:Redmond
```

---

> **シナリオ 5:** URL フィルターを更新する

   ![URL フィルターの更新](./media/url-filter-5.png)

***コマンドレット***

[Set-CsImFilterConfiguration](/powershell/module/skype/set-csimfilterconfiguration)

***例***

```powershell
 Set-CsImFilterConfiguration -Identity site:Redmond -Enabled $False
```

---
