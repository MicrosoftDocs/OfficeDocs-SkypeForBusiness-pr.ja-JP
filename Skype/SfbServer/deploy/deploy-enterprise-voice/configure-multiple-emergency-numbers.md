---
title: Skype for Business で複数の緊急電話番号を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 81d3dbed919c936eb8a656d123f5c44e445044d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027798"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Skype for Business で複数の緊急電話番号を構成する

このトピックでは、Skype for Business Server で複数の緊急電話番号を構成する方法について説明します。

Skype for Business Server は、クライアントの複数の緊急電話番号をサポートするようになりました。 複数の緊急電話番号は、2016年6月の累積的な更新プログラムで導入された新機能です。 複数の緊急電話番号をサポートするように環境を構成する前に、 [Skype For Business Server の複数の緊急電話番号の計画](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)を必ずお読みください。

> [!NOTE]
> 2016年11月の累積的な更新プログラムにまだアップグレードしていない場合は、「 [Skype For Business Server 2015 の更新プログラム](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)」を参照してください。 2016年11月の累積的な更新プログラムでは、サポートの緊急電話番号の数は5から100に増加します。

## <a name="configure-multiple-emergency-numbers"></a>複数の緊急電話番号を構成する

複数の緊急電話番号を構成するには、New-csemergencynumber コマンドレットを使用して、EmergencyNumbers パラメーターを[新しい-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)および[Set-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)コマンドレットと共に指定します。 PSTN 使用法や必要な場所など、すべての場所ポリシーパラメーターの詳細については、「 [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)」を参照してください。

次のコマンドは、CsEmergency コマンドレットを使用して、ダイヤル文字列911を使用して新しい緊急電話番号を作成します。

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

次のコマンドは、EmergencyNumbers パラメーターを指定して、指定された場所のポリシーに番号を関連付けます。

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

次の例では、1つのダイヤルマスク112で緊急電話番号が作成されます。

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

次のコマンドは、複数のダイヤルマスクを持つ緊急電話番号を作成します。

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

次の例では、複数のダイヤルマスクを持つ複数の緊急電話番号を追加し、緊急電話番号を指定された場所のポリシーに関連付けます。

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

次の例では、911と450の両方を使用する医療機関向けに複数の緊急電話番号を構成します。

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

次の例では、London の市に対して複数の緊急電話番号を構成します。

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

次の例では、ダイヤル文字列911とダイヤルマスク112および999を使用して既存のエントリを削除します。

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
