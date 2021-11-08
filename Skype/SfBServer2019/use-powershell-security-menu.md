---
title: '[セキュリティ] メニューのタスクに PowerShell を使用する'
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
description: '概要: [Skype for Business Serverのコマンドレット マッピング] メニューに移動します。'
ms.openlocfilehash: 6e726b13b9428b213011126abf5ac0869e6cfbf8
ms.sourcegitcommit: eba9fc680233e9e03773a2942f22afe6247eec41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60824934"
---
# <a name="security"></a>セキュリティ

この記事では、従来のコントロール パネルの[セキュリティ] メニュー項目と同様の結果をコマンドレットを使用してどのように実現できるのかについて説明します。

この記事では、次のサブメニューについて説明します。

- [セキュリティ](#security)
  - [レジストラー](#registrar)
  - [Web サービス](#web-service)
  - [PIN ポリシー](#pin-policy)

## <a name="registrar"></a>レジストラー

**REGISTRAR** サブメニューを使用すると、管理者はプロキシ サーバー構成設定を使用してプロキシ サーバーを管理できます。 これらの設定は、グローバル スコープとサービス スコープの両方 (エッジ サーバーとレジストラー サービスのみ) で適用できます。これにより、クライアント エンドポイントで使用できる認証プロトコルや、着信プロキシ サーバー接続と発信プロキシ サーバー接続で圧縮が使用されるかどうかを制御できます。

レジストラーでユーザーが実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessするコマンドレットについて考えさせてください。

---

> **シナリオ 1**: すべてのプロキシ構成を一覧表示する

   ![リスト プロキシの構成](./media/proxy-configurations-1.png)

***コマンドレット***

[Get-CsProxyConfiguration](/powershell/module/skype/get-csproxyconfiguration)

***例***

```powershell
 Get-CsProxyConfiguration
```

---

> **シナリオ 2:** 新しいプロキシ構成を作成する

   ![プロキシ構成の作成](./media/proxy-configurations-2.png)

***コマンドレット***

[New-CsProxyConfiguration](/powershell/module/skype/new-csproxyconfiguration)  

***例***

```powershell
 New-CsProxyConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -RequestServerCompression $True -MaxClientMessageBodySizeKb 256
```

---

> **シナリオ 3:** 選択したプロキシ構成の詳細を取得する

   ![プロキシ構成の取得](./media/proxy-configurations-3.png)

***コマンドレット***

[Get-CsProxyConfiguration](/powershell/module/skype/get-csproxyconfiguration)

***例***

```powershell
 Get-CsProxyConfiguration -Identity "service:EdgeServer:atl-cs-001.litwareinc.com"
```

---

> **シナリオ 4:** 選択したプロキシ構成を削除する

   ![プロキシ構成の削除](./media/proxy-configurations-4.png)

***コマンドレット***

[Remove-CsProxyConfiguration](/powershell/module/skype/remove-csproxyconfiguration)

***例***

```powershell
 Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
```

---

> **シナリオ 5**: プロキシ構成を更新する

   ![プロキシ構成の更新](./media/proxy-configurations-5.png)

***コマンドレット***

[Set-CsProxyConfiguration](/powershell/module/skype/set-csproxyconfiguration)

***例***

```powershell
 Set-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-001.litwareinc.com -AcceptServerCompression $True
```

---

## <a name="web-service"></a>(Web) サービス

[ **セキュリティ] の [WEB サービス** ] サブメニュー項目を **使用すると、** 管理者は組織全体で Web サービス構成設定を管理できます。これには、グループ展開、証明書の設定、許可された認証方法の管理が含まれます。 管理者はグローバル スコープ、サイト スコープ、およびサービス スコープ (Web Services サービスのみ) で異なる設定を構成できるので、ユーザーや場所ごとに Web サービス機能をカスタマイズできます。

WEB SERVICE でユーザーが実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessコマンドレットについて説明します。

---
> **シナリオ 1**: すべての Web サービス構成を一覧表示する

   ![Web サービス構成の一覧表示](./media/web-service-1.png)

***コマンドレット***

[Get-CsWebServiceConfiguration](/powershell/module/skype/get-cswebserviceconfiguration)

***例***

```powershell
 Get-CsWebServiceConfiguration
```

---

> **シナリオ 2:** 新しい Web サービス構成を作成する

   ![新しい Web サービス構成](./media/web-service-2.png)

***コマンドレット***

[New-CsWebServiceConfiguration](/powershell/module/skype/new-cswebserviceconfiguration)  

***例***

```powershell
 New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True
```

---

> **シナリオ 3:** 選択した Web サービス構成の詳細を取得する

   ![Web サービス構成の取得](./media/web-service-3.png)

***コマンドレット***

[Get-CsWebServiceConfiguration](/powershell/module/skype/get-cswebserviceconfiguration)

***例***

```powershell
 Get-CsWebServiceConfiguration -Identity site:Redmond
```

---

> **シナリオ 4:** 選択した Web サービス構成を削除する

   ![Web サービス構成の削除](./media/web-service-4.png)

***コマンドレット***

[Remove-CsWebServiceConfiguration](/powershell/module/skype/remove-cswebserviceconfiguration)

***例***

```powershell
 Remove-CsWebServiceConfiguration -Identity site:Redmond
```

---

> **シナリオ 5:** Web サービス構成の更新

   ![Web サービス構成の更新](./media/Web-service-5.png)

***コマンドレット***

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration)

***例***

```powershell
 Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True
```

---

## <a name="pin-policy"></a>PIN ポリシー

管理者は **、PIN ポリシーを使用して** PIN 認証プロパティを管理できます。たとえば、PIN の最小長を指定し、連続する数字などの "共通パターン" を使用する PIN を許可するかどうかを決定できます (たとえば、pin など123456)

**PIN** POLICY でユーザーが実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessするコマンドレットについて検討します。

---

> **シナリオ 1**: すべての PIN ポリシーを一覧表示する

   ![リスト ピン ポリシー](./media/pin-policy-1.png)

***コマンドレット***

[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy)

***例***

```powershell
 Get-CsPinPolicy
```

---

> **シナリオ 2:** 新しい PIN ポリシーを作成する

   ![ピン ポリシーの作成](./media/pin-policy-2.png)

***コマンドレット***

[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy)  

***例***

```powershell
 New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 10
```

---

> **シナリオ 3:** 選択した PIN ポリシーの詳細を取得する

   ![PIN ポリシーの取得](./media/pin-policy-3.png)

***コマンドレット***

[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy)

***例***

```powershell
 Get-CsPinPolicy -Identity "site:Redmond"
```

---

> **シナリオ 4**: 選択した PIN ポリシーを削除する

   ![PIN ポリシーの削除](./media/pin-policy-4.png)

***コマンドレット***

[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy)

***例***

```powershell
 Remove-CsPinPolicy -Identity RedmondUsersPinPolicy
```

---

> **シナリオ 5**: PIN ポリシーを更新する

   ![PIN ポリシーの更新](./media/pin-policy-5.png)

***コマンドレット***

[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy)

***例***

```powershell
 Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

---
