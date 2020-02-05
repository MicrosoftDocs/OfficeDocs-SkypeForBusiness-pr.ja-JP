---
title: Skype for Business の複数の緊急電話番号を設定する
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
description: Skype for Business Server で複数の緊急電話番号を設定する方法については、こちらのトピックを参照してください。
ms.openlocfilehash: 9805462d8c9498af3e3cf1cb743e2af9e08ec285
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768120"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Skype for Business の複数の緊急電話番号を設定する

Skype for Business Server で複数の緊急電話番号を設定する方法については、こちらのトピックを参照してください。

Skype for Business Server で、クライアントの複数の緊急電話番号がサポートされるようになりました。 複数の緊急電話番号は、2016年6月の累積更新プログラムで導入された新機能です。 複数の緊急電話番号をサポートするように環境を構成する前に、「 [Skype For Business Server で複数の緊急電話番号のプラン](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)を確認する」を参照してください。

> [!NOTE]
> 2016年11月の累積更新プログラムにアップグレードしていない場合は、「 [Skype For Business Server 2015 の更新プログラム](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)」を参照してください。 2016年11月の累積更新プログラムでは、サポート緊急電話番号の数が5から100に増えます。 

## <a name="configure-multiple-emergency-numbers"></a>複数の緊急電話番号の構成

複数の緊急電話番号を構成するには、CsEmergencyNumber コマンドレットを使用します。次に、[新しい-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)と[Set-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)コマンドレットを使用して、EmergencyNumbers パラメーターを指定します。 PSTN の使用状況や必要な場所など、すべての場所ポリシーパラメーターの詳細については、「 [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)」を参照してください。

次のコマンドでは、New-CsEmergency コマンドレットを使用して、ダイヤル文字列 911 で新しい緊急電話番号を作成します。

```powershell
> $a = New-CsEmergencyNumber -DialString 911 
```

次のコマンドでは、Set-CsLocationPolicy コマンドレットで EmergencyNumbers パラメータを指定して、番号を特定の場所のポリシーに関連付けます。

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 
```

次の例では、1 つのダイヤル マスク 112 を持つ緊急電話番号が作成されます。

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 
```

次のコマンドでは、複数のダイヤルマスクを持つ緊急電話番号を作成します。

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
```

次の例では、複数のダイヤル マスクを持つ複数の緊急電話番号を追加し、緊急電話番号を特定の場所のポリシーに関連付けます。

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 
```

次の例では、911 と 450 の両方を使用する医療機関向けに複数の緊急電話番号を構成します。  

```powershell
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

次の例では、ロンドン シティー向けに複数の緊急電話番号を構成します。

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

次の例では、インド向けに複数の緊急電話番号を構成します。

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

次の例では、ダイヤル文字列 911 およびダイヤル マスク 112 と 999 を持つ既存のエントリを削除します。

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 
```


