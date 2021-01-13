---
title: Skype for Business Server で複数の緊急電話番号を計画する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: このトピックでは、Skype for Business Server で複数の緊急電話番号を計画する方法について説明します。
ms.openlocfilehash: eb5fbc55bc7f2e783fbfa98c7bc7fb6db67ff748
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813867"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Skype for Business Server で複数の緊急電話番号を計画する
 
このトピックでは、Skype for Business Server で複数の緊急電話番号を計画する方法について説明します。
  
Skype for Business Server では、クライアントの複数の緊急電話番号の構成がサポートされます。 複数の緊急電話番号は、2016 年 6 月の累積的な更新プログラムで導入された新機能です。 米国の緊急電話番号は 911 ですが、多くの国では複数の緊急電話番号がサポートされています。 たとえば、英国は、英国固有の緊急電話番号である 999 と欧州連合の緊急電話番号 112 の両方をサポートしています。 
  
この機能は、複数のコードブルー緊急電話番号のローミング サポートを必要としている米国内の医療プロバイダーにも役立ちます。
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>複数の緊急電話番号と場所のポリシー

緊急通話を構成するには、緊急通話の実装方法を定義する場所ポリシーを作成します。 場所ポリシーを使用して、緊急電話を構成する番号 (米国の 911 など) を定義します。英国の 999 および 112。 場所ポリシーは、ユーザーが緊急通話を有効にするかどうか、有効になっている場合は緊急電話の動作を決定します。 また、企業のセキュリティに自動的に通知するかどうか、および通話のルーティング方法を定義することもできます。
  
場所ポリシーの定義と変更の詳細については [、「Plan location policies for Skype for Business Server](location-policies.md) and Create location [policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md)」を参照してください。 これらのトピックでは、場所のポリシーに関する概念について説明します。ただし [、「Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) で複数の緊急電話番号を構成する」の手順に従って、複数の緊急電話番号を構成する必要があります。
  
複数の緊急電話番号を計画する場合は、以下の注意が必要です。
  
- 2016 年 6 月の累積的な更新プログラムでは、特定の場所のポリシーに対して最大 5 つの緊急電話番号を定義できます。 2016 年 11 月の累積的な更新プログラムでは、この数は 100 に増加します。
    
    > [!NOTE]
    > If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). 
  
- 緊急電話番号ごとに、特定の場所のポリシーに固有の 0 個以上の緊急ダイヤル マスクを指定できます。
    
    ダイヤル マスクは、ダイヤル時に緊急ダイヤル番号の値に変換する番号です。 たとえば、このフィールドに値 212 を入力し、緊急ダイヤル番号フィールドの値を 911 とします。 ユーザーが 212 をダイヤルすると、番号は 911 に変換されます。 これにより、別の緊急電話番号をダイヤルし、緊急サービスに通話を発信できます (たとえば、緊急電話番号が異なる国または地域のユーザーが、現在の国または地域の番号ではなく、その国または地域の番号にダイヤルしようとした場合)。 値をセミコロン (;) で区切って複数の緊急ダイヤル マスクを定義できます。 たとえば、212;414 などです。 ダイヤル マスクの文字列の制限は 100 文字です。 各文字は 0 ～ 9 の数字である必要があります。
    
- 各場所ポリシーには、このポリシーを使用するクライアントからの緊急通話をルーティングするために使用するボイス ルートを決定するために使用される、単一の公衆交換電話網 (PSTN) 使用法があります。 使用法には、緊急電話番号ごとに一意のルートを設定できます。
    
- 場所ポリシーに EmergencyNumbers パラメーターと DialString パラメーターの両方が定義され、クライアントが複数の緊急電話番号をサポートしている場合は、緊急電話番号が優先されます。 クライアントが複数の緊急電話番号をサポートしていない場合は、緊急ダイヤル文字列が使用されます。
    
- Skype for Business および Lync クライアントが複数の緊急電話番号、ダイヤル マスク、公衆交換電話網 (PSTN) 使用法の受信をサポートする方法については、「クライアント サポート」を参照 [してください](multiple-emergency-numbers.md#BKMK_Clients)。
    
> [!NOTE]
> Skype for Business コントロール パネルを使用して複数の緊急電話番号を構成することはできません。 複数の緊急電話番号を構成するには、PowerShell を使用する必要があります。 
  
複数の緊急電話番号を構成する前に、次の注意を行います。
  
- 複数の緊急電話番号を構成するには、New-CsEmergencyNumber コマンドレットを使用する必要があります。また [、New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) コマンドレットと [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) コマンドレットで EmergencyNumbers パラメーターを指定して、複数の緊急電話番号をサポートする場所ポリシーを定義する必要があります。
    
- EmergencyDialString パラメーターと EmergencyDialMask パラメーターを指定して Set-CsLocationPolicy または New-CsLocationPolicy コマンドレットを使用して定義された既存の番号がある場合、EmergencyNumbers パラメーターで指定された値は、古い値よりも優先されます。 つまり、EmergencyDialString パラメーターと EmergencyDialMask パラメーターの値は無視されます。
    
- EmergencyDialString パラメーターと EmergencyDialMask パラメーターを指定して Set-CsLocationPolicy または New-CsLocationPolicy コマンドレットを使用して既存の番号を定義し、新しい緊急電話番号を構成しない場合、既存の番号は引き続き使用されます。
    
- 複数の緊急電話番号機能が機能するには、実行中のクライアント バージョンが新しい機能をサポートできる必要があります。 古いクライアントは、EmergencyDialString パラメーターと EmergencyDialMask パラメーターを指定した Set-CsLocationPolicy または New-CsLocationPolicy コマンドレットで指定された古い値を引き続き使用します。 
    
- ユーザーがダイヤル文字列と一致する番号をダイヤルする場合、ダイヤル マスクは必要ありません。 たとえば、ユーザーがダイヤルする番号が 911 の場合、ダイヤル文字列は 911 で、マスクは必要ありません。 
    
複数の緊急電話番号の構成の詳細については、「Skype for Business で複数の緊急電話番号を構成する」 [を参照してください](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)。
  
次の表に、場所ポリシーの例を示します (この例では、すべての属性が示されているのではありません)。
  

|**場所ポリシー名**|**E911 が有効**|**緊急ダイヤル文字列**|**ダイヤル マスク**|**緊急電話番号**|**PSTN 使用法**|**必要な場所**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|米国  <br/> |必要  <br/> |911  <br/> | 112;999 <br/> ||USEmergency  <br/> |必要  <br/> |
|US-Hospital  <br/> |必要  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |必要  <br/> |
|ロンドン  <br/> |必要  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911;117;118  <br/> |GBEmergency  <br/> |いいえ  <br/> |
|インド  <br/> |必要  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |いいえ  <br/> |
   
 **米国 —** 複数の緊急電話番号の要件はありません。 米国では、古い緊急ダイヤル文字列およびダイヤル マスク構成を使用します。
  
 **US-Hospital** —"450" をマスクしない必要があります。 複数の緊急電話番号をまだサポートしていないクライアントの場合は、古い緊急ダイヤル文字列およびダイヤル マスク構成を使用できます。 複数の緊急電話番号をサポートするクライアントの場合は、450 をマスクする代わりに、"911" と "450" の両方に緊急電話番号を定義できます。
  
 **London** - 複数の緊急電話番号をまだサポートしていないクライアントの場合は、古い緊急ダイヤル文字列およびダイヤル マスク構成を使用できます。 複数の緊急電話番号をサポートするクライアントの場合は、"999" と "112" の両方の緊急電話番号をマスク付きで定義できます。
  
 **インド** — 展開されているクライアントはすべて、複数の緊急電話番号をサポートしています。 インドでは、複数の緊急電話番号を構成する必要があります。
  
## <a name="client-support"></a>クライアント サポート
<a name="BKMK_Clients"> </a>

次の表に、複数の緊急電話番号に対するクライアント サポートを示します。 Microsoft は引き続き、追加のクライアントのサポートをテストしてリリースします。 頻繁に確認してください。

|**Windows**|**バージョン**|
|:-----|:-----|
|**クイック実行** <br/> |CC (Current Channel) released on May 10, 2016 - Version 1604 (Build 6868.2062)  <br/> |
||FRDC (First Release Current Channel) released on June 14, 2016 - Version 1605 (Build 6965.2058)  <br/> |
||2016 年 10 月 11 日にリリースされた DC (Deferred Channel) - バージョン 1605 (ビルド 6965.2092)  <br/> |
|**MSI** <br/> |6 月 7 日の更新プログラム - [https://support.microsoft.com/kb/3115087](https://support.microsoft.com/kb/3115087) <br/> |
|**Mac と iOS** <br/> |**バージョン** <br/> |
||Skype for Business Mac クライアント バージョン 16.9  <br/> Skype for Business iOS クライアント バージョン 6.16  <br/> |
|**Android** <br/> |**バージョン** <br/> |
||Skype for Business Android クライアント バージョン 6.17  <br/> |
|**Lync Phone Edition** <br/> |**バージョン** <br/> |
|| Aastra 6721ip および Aastra 6725ip 電話機 - 2016 年 9 月の累積的な更新プログラム (ビルド 7577.4512) -[https://support.microsoft.com/kb/3194831](https://support.microsoft.com/kb/3194831) <br/> |
|| HP 4110 および HP 4120 電話 - 2016 年 9 月の累積的な更新プログラム (ビルド 7577.4512) -[https://support.microsoft.com/kb/3194832](https://support.microsoft.com/kb/3194832) <br/> |
||Polycom CX500、Polycom CX600、および Polycom CX3000 電話機 - 2016 年 9 月の累積的な更新プログラム (ビルド 7577.4512) - [https://support.microsoft.com/kb/3194833](https://support.microsoft.com/kb/3194833) <br/> |
   

