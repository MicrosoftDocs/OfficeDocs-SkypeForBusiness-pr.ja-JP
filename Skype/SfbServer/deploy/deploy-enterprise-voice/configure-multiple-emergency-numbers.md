---
title: Skype for Business 2015 での複数の緊急電話番号を構成する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 4/21/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: このトピックでは、Skype for Business Server 2015 で複数の緊急電話番号を構成する方法について説明します。
ms.openlocfilehash: 98d9bbef92f5f3894fb288c01e474288f9f7bb4c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business-2015"></a>Skype for Business 2015 での複数の緊急電話番号を構成する
 
このトピックでは、Skype for Business Server 2015 で複数の緊急電話番号を構成する方法について説明します。
  
Skype ビジネス サーバーがクライアントの複数の緊急番号をサポートしています。 複数の緊急番号は 2016年 6 月で導入された新しい機能を累積的な更新です。 複数の緊急番号をサポートするために、環境を構成する前に、[ビジネス サーバー 2015 の Skype で緊急番号が複数の計画](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)を参照してください。
  
> [!NOTE]
> かどうかにないまだアップグレード 2016年 11 月累積的な更新は、 [Skype のビジネス サーバー 2015 への更新](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)を参照してください。 2016年 11 月の累積的な更新をサポート緊急時の番号の数は 5 から 100 に増加します。 
  
## <a name="configure-multiple-emergency-numbers"></a>複数の緊急電話番号の構成

複数の緊急番号を構成するのには、新規 CsEmergencyNumber コマンドレットを使用して[新規 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)と[セット CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)コマンドレットの EmergencyNumbers パラメーターを指定するし。 すべての場所ポリシーのパラメーター、PSTN の使用法など、必要な場所の詳細については、[セット CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)を参照してください。
  
次のコマンドでは、New-CsEmergency コマンドレットを使用して、ダイヤル文字列 911 で新しい緊急電話番号を作成します。
  
```
> $a = New-CsEmergencyNumber -DialString 911 

```

次のコマンドでは、Set-CsLocationPolicy コマンドレットで EmergencyNumbers パラメータを指定して、番号を特定の場所のポリシーに関連付けます。
  
```
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 

```

次の例では、1 つのダイヤル マスク 112 を持つ緊急電話番号が作成されます。
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 

```

次のコマンドは、複数のダイヤル マスクを使用した、緊急電話番号を作成します。
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 

```

次の例では、複数のダイヤル マスクを持つ複数の緊急電話番号を追加し、緊急電話番号を特定の場所のポリシーに関連付けます。
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 

```

次の例では、911 と 450 の両方を使用する医療機関向けに複数の緊急電話番号を構成します。  
  
```
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

次の例では、ロンドン シティー向けに複数の緊急電話番号を構成します。
  
```
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}

```

次の例では、インド向けに複数の緊急電話番号を構成します。
  
```
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}

```

次の例では、ダイヤル文字列 911 およびダイヤル マスク 112 と 999 を持つ既存のエントリを削除します。
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 

```


