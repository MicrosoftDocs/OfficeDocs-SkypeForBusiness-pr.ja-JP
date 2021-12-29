---
title: '[監視とアーカイブ] メニューのタスクに PowerShell を使用する'
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
description: '概要: [監視Skype for Business Serverアーカイブ] メニューのコマンドレット マッピングにコントロール パネルを表示します。'
ms.openlocfilehash: b286cf1ad1f52e67c4e4171402927c24908aa4ac
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626231"
---
# <a name="monitoring-and-archiving"></a>監視およびアーカイブ

この記事では、従来のコントロール パネルの[監視とアーカイブ] メニュー項目と同様の結果をコマンドレットを使用してどのように実現できるのかについて説明します。

この記事では、次のサブメニューについて説明します。

- [監視およびアーカイブ](#monitoring-and-archiving)
  - [通話詳細記録](#call-detail-recording)
  - [Quality of Experience Data](#quality-of-experience-data)
  - [アーカイブ ポリシー](#archiving-policy)
  - [アーカイブ構成](#archiving-configuration)

## <a name="call-detail-recording"></a>通話詳細記録

**CALL DETAIL RECORDING** サブメニューを使用すると、管理者は通話詳細記録 (CDR) 設定を管理できます。CDR を使用すると、ピアツーピア のインスタント メッセージング セッション、Voice over Internet Protocol (VoIP) 通話、電話会議などの使用状況を追跡できます。

ユーザーが CALL **DETAIL RECORDING** で実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessするコマンドレットについて説明します。

---

> **シナリオ 1**: すべての CDR 構成を一覧表示する

   ![リスト Cdr の構成](./media/cdr-configurations-1.png)

***コマンドレット***

[Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration)

***例***

```powershell
 Get-CsCdrConfiguration
```

---

> **シナリオ 2:** 新しい CDR 構成を作成する

   ![Cdr 構成の作成](./media/cdr-configurations-2.png)

***コマンドレット***

[New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration)  

***例***

```powershell
 New-CsCdrConfiguration -Identity site:Redmond -EnableCDR $False
```

---

> **シナリオ 3:** 選択した CDR 構成の詳細を取得する

   ![Cdr の構成を取得する](./media/cdr-configurations-3.png)

***コマンドレット***

[Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration)

***例***

```powershell
 Get-CsCdrConfiguration -Identity site:Redmond
```

---

> **シナリオ 4**: 選択した CDR 構成を削除する

   ![Cdr 構成の削除](./media/cdr-configurations-4.png)

***コマンドレット***

[Remove-CsCdrConfiguration](/powershell/module/skype/remove-cscdrconfiguration)

***例***

```powershell
 Remove-CsCdrConfiguration -Identity site:Redmond
```

---

> **シナリオ 5**: CDR 構成を更新する

   ![Cdr 構成の更新](./media/cdr-configurations-5.png)

***コマンドレット***

[Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration)

***例***

```powershell
 Set-CsCdrConfiguration -Identity site:Redmond -PurgeHourOfDay 23
```

---

## <a name="quality-of-experience-data"></a>Quality of Experience Data

[QUALITY **OF EXPERIENCE DATA]** サブメニューを使用すると、管理者は QoE (Quality of Experience) 設定を管理できます。 組織全体で。これには、グループ展開、証明書の設定、許可された認証方法の管理が含まれます。 管理者はグローバル スコープ、サイト スコープ、およびサービス スコープ (Web Services サービスのみ) で異なる設定を構成できるので、ユーザーや場所ごとに Web サービス機能をカスタマイズできます。

WEB SERVICE でユーザーが実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessコマンドレットについて説明します。

---
> **シナリオ 1**: すべての QoE 構成を一覧表示する

   ![QoE 構成の一覧](./media/qoe-configuration-1.png)

***コマンドレット***

[Get-CsQoEConfiguration](/powershell/module/skype/get-csqoeconfiguration)

***例***

```powershell
 Get-CsQoEConfiguration
```

---

> **シナリオ 2:** 新しい QoE 構成を作成する

   ![新しい QoE 構成](./media/qoe-configuration-2.png)

***コマンドレット***

[New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration)  

***例***

```powershell
 New-CsQoEConfiguration -Identity site:Redmond -EnableQoE $False
```

---

> **シナリオ 3:** 選択した QoE 構成の詳細を取得する

   ![QoE 構成の取得](./media/qoe-configuration-3.png)

***コマンドレット***

[Get-CsQoEConfiguration](/powershell/module/skype/get-csqoeconfiguration)

***例***

```powershell
 Get-CsQoEConfiguration -Identity site:Redmond
```

---

> **シナリオ 4**: 選択した QoE 構成を削除する

   ![QoE 構成の削除](./media/qoe-configuration-4.png)

***コマンドレット***

[Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration)

***例***

```powershell
 Remove-CsQoEConfiguration -Identity site:Redmond
```

---

> **シナリオ 5**: QoE 構成を更新する

   ![QoE 構成の更新](./media/qoe-configuration-5.png)

***コマンドレット***

[Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration)

***例***

```powershell
 Set-CsQoEConfiguration -Identity site:Redmond -EnableQoE $False
```

---

## <a name="archiving-policy"></a>アーカイブ ポリシー

管理者は、 **アーカイブ ポリシーを使用して** インスタント メッセージング (IM) セッション アーカイブ ポリシーを管理できます。アーカイブ ポリシーを使用すると、内部ユーザー間または内部ユーザーと外部ユーザーの間で行うすべての IM および Web 会議セッションをアーカイブできます。

ユーザーがアーカイブ ポリシーで実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessコマンドレットについて検討します。

---

> **シナリオ 1**: すべてのアーカイブ ポリシーを一覧表示する

   ![リスト アーカイブ ポリシー](./media/archiving-policy-1.png)

***コマンドレット***

[Get-CsArchivingPolicy](/powershell/module/skype/get-csarchivingpolicy)

***例***

```powershell
 Get-CsArchivingPolicy
```

---

> **シナリオ 2:** 新しいアーカイブ ポリシーを作成する

   ![アーカイブ ポリシーの作成](./media/archiving-policy-2.png)

***コマンドレット***

[New-CsArchivingPolicy](/powershell/module/skype/new-csarchivingpolicy)  

***例***

```powershell
 New-CsArchivingPolicy -Identity site:Redmond -ArchiveInternal $True
```

---

> **シナリオ 3:** 選択したアーカイブ ポリシーの詳細を取得する

   ![アーカイブ ポリシーの取得](./media/archiving-policy-3.png)

***コマンドレット***

[Get-CsArchivingPolicy](/powershell/module/skype/get-csarchivingpolicy)

***例***

```powershell
 Get-CsArchivingPolicy -Identity site:Redmond
```

---

> **シナリオ 4:** 選択したアーカイブ ポリシーを削除する

   ![アーカイブ ポリシーの削除](./media/archiving-policy-4.png)

***コマンドレット***

[Remove-CsArchivingPolicy](/powershell/module/skype/remove-csarchivingpolicy)

***例***

```powershell
 Remove-CsArchivingPolicy -Identity site:Redmond
```

---

> **シナリオ 5:** アーカイブ ポリシーを更新する

   ![アーカイブ ポリシーの更新](./media/archiving-policy-5.png)

***コマンドレット***

[Set-CsArchivingPolicy](/powershell/module/skype/set-csarchivingpolicy)

***例***

```powershell
 Set-CsArchivingPolicy -Identity global -ArchiveInternal $True
```

---

## <a name="archiving-configuration"></a>アーカイブ構成

管理者は、 **アーカイブ構成を使用して** 、組織内でインスタント メッセージング (IM) セッションをアーカイブする方法 (または場合) を構成できます。

ユーザーがアーカイブ構成で実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessコマンドレットについて考えさせてください。

---

> **シナリオ 1**: すべてのアーカイブ構成を一覧表示する

   ![リスト アーカイブの構成](./media/archiving-configuration-1.png)

***コマンドレット***

[Get-CsArchivingConfiguration](/powershell/module/skype/get-csarchivingconfiguration)

***例***

```powershell
 Get-CsArchivingConfiguration
```

---

> **シナリオ 2:** 新しいアーカイブ構成を作成する

   ![アーカイブ構成の作成](./media/archiving-configuration-2.png)

***コマンドレット***

[New-CsArchivingConfiguration](/powershell/module/skype/new-csarchivingconfiguration)  

***例***

```powershell
 New-CsArchivingConfiguration -Identity site:Redmond -EnableArchiving "ImOnly"
```

---

> **シナリオ 3:** 選択したアーカイブ構成の詳細を取得する

   ![アーカイブ構成の取得](./media/archiving-configuration-3.png)

***コマンドレット***

[Get-CsArchivingConfiguration](/powershell/module/skype/get-csarchivingconfiguration)

***例***

```powershell
 Get-CsArchivingConfiguration -Identity site:Redmond
```

---

> **シナリオ 4:** 選択したアーカイブ構成を削除する

   ![アーカイブ構成の削除](./media/archiving-configuration-4.png)

***コマンドレット***

[Remove-CsArchivingConfiguration](/powershell/module/skype/remove-csarchivingconfiguration)

***例***

```powershell
 Remove-CsArchivingConfiguration -Identity site:Redmond
```

---

> **シナリオ 5**: アーカイブ構成を更新する

   ![アーカイブ構成の更新](./media/archiving-configuration-5.png)

***コマンドレット***

[Set-CsArchivingConfiguration](/powershell/module/skype/set-csarchivingconfiguration)

***例***

```powershell
 Set-CsArchivingConfiguration -Identity site:Redmond -ArchiveDuplicateMessages $False -KeepArchivingDataForDays 30
```

---
