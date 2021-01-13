---
title: Skype for Business で複数の緊急電話番号を構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: このトピックでは、Skype for Business Server で複数の緊急電話番号を構成する方法について説明します。
ms.openlocfilehash: fe53e914eb0c406a4f7013df2f6ec106fa781f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804107"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Skype for Business で複数の緊急電話番号を構成する

このトピックでは、Skype for Business Server で複数の緊急電話番号を構成する方法について説明します。

Skype for Business Server では、クライアントで複数の緊急電話番号がサポートされます。 複数の緊急電話番号は、2016 年 6 月の累積的な更新プログラムで導入された新機能です。 複数の緊急電話番号をサポートする環境を構成する前に [、「Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)で複数の緊急電話番号を計画する」を参照してください。

> [!NOTE]
> If you have yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). 2016 年 11 月の累積的な更新プログラムでは、サポート緊急電話番号の数が 5 から 100 に増加しました。

## <a name="configure-multiple-emergency-numbers"></a>複数の緊急電話番号の構成

複数の緊急電話番号を構成するには、New-CsEmergencyNumber コマンドレットを使用し [、New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) コマンドレットと [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) コマンドレットを使用して EmergencyNumbers パラメーターを指定します。 PSTN 使用法や必要な場所など、すべての場所ポリシー パラメーターの詳細については [、「Set-CsLocationPolicy」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)。

次のコマンドは、次のコマンドレットを使用して、ダイヤル文字列 911 を持つ新しい緊急New-CsEmergencyします。

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

次のコマンドでは、次のコマンドレットで EmergencyNumbers パラメーターを指定して、番号を指定した場所のポリシーSet-CsLocationPolicyします。

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

次の例では、1 つのダイヤル マスク 112 で緊急電話番号が作成されます。

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

次のコマンドは、複数のダイヤル マスクを持つ緊急電話番号を作成します。

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

次の例では、複数のダイヤル マスクを持つ複数の緊急電話番号を追加し、緊急電話番号を指定された場所のポリシーに関連付します。

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

次の例では、911 と 450 の両方を使用する医療プロバイダー用に複数の緊急電話番号を構成します。

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

次の例では、ロンドン市の複数の緊急電話番号を構成します。

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

次の例では、インドの複数の緊急電話番号を構成します。

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

次の例では、ダイヤル文字列 911 とダイヤル マスク 112 および 999 の既存のエントリを削除します。

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
