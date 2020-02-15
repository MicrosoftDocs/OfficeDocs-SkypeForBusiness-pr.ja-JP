---
title: 先進認証でサポートされている Skype for Business のトポロジ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: この記事では、Skype for Business での先進認証でサポートされるオンラインおよびオンプレミスのトポロジと、各トポロジに適用されるセキュリティ機能について説明します。
ms.openlocfilehash: b23c2081833b43f0f734febc0b18356abf63506e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043759"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>先進認証でサポートされている Skype for Business のトポロジ
 
この記事では、Skype for Business での先進認証でサポートされるオンラインおよびオンプレミスのトポロジと、各トポロジに適用されるセキュリティ機能について説明します。
  
## <a name="modern-authentication-in-skype-for-business"></a>Skype for Business での先進認証

Skype for Business は先進認証のセキュリティ上の利点を活用できます。 Skype for Business は Exchange と密接に連携するため、Skype for Business クライアントユーザーに表示されるログイン動作も、Exchange の MA の状態によって影響を受けます。 このことは、Skype for Business の分割ドメインハイブリッドを使用している場合にも適用されます。 これはさまざまな可動パーツですが、ここでの目的は、サポートされるトポロジのリストを簡単に表示できることです。
  
特定の Skype for Business、Skype for Business online、Exchange Server、および Exchange online の場合、MA でサポートされているトポロジは何ですか。
  
<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. --> 
  
### <a name="supported-ma-topologies-in-skype-for-business"></a>Skype for Business でサポートされている MA トポロジ

2つのサーバーアプリケーションがあり、MA が使用する Skype for Business のトポロジには2つの Office 365 ワークロードが関係しています。
  
- Skype for Business server (CU 5) オンプレミス
    
- Skype for Business online (SFBO)
    
- オンプレミスの Exchange サーバー
    
- Exchange server online (EXO)
    
MA のもう1つの重要な部分は、ユーザーの認証 (認証) と承認 (authZ) がどこで行われるかを知ることです。 2つのオプションは次のとおりです。
  
- Azure AD、Microsoft クラウドのオンライン
    
- オンプレミスの Active Directory フェデレーションサーバー (ADFS)
    
このように、Azure AD を使用したクラウドでの EXO と SFBO、オンプレミスの Exchange Server (EXCH) および Skype for Business server (SFB) を使用します。
  
![すべてのアプリケーション (Exchange と Skype for business) とワークロード (EXO と SFBO) の例と、MA を有効にする際に関係する認証サーバー (ADFS と evoSTS) の両方を示します。](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)
  
サポートされているトポロジを次に示します。 グラフィックスのキーに注意してください。
  
- アイコンが淡色表示または灰色の場合、このシナリオでは使用されません。
    
- EXO は Exchange Online です。
    
- SFBO は、Skype for Business Online です。
    
- EXCH はオンプレミスの Exchange です。
    
- SFB は、オンプレミスの Skype for Business です。
    
- 承認するサーバーは三角形で表されます。たとえば、Azure AD は、その背後に雲がある三角形になります。
    
- 矢印は、クライアントが指定されたサーバーリソースに到達しようとするときに使用する認証サーバーを指しています。
    
最初に、オンプレミスのみのトポロジまたはクラウド専用のトポロジの両方で Skype for Business を使用して MA を取り上げましょう。
  
> [!IMPORTANT]
> Skype for Business Online で先進認証をセットアップする準備ができましたか? この機能を有効にする手順は[次](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)のとおりです。 
  
|トポロジ名  <br/> |例  <br/> |説明  <br/> |サポートされている  <br/> |
|:-----|:-----|:-----|:-----|
|クラウドのみ  <br/> |![MA のトポロジでサポートされている SFB、クラウドのみ。](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)ユーザーの所属/メールボックスの場所: オンライン  <br/> |MA は EXO と SFBO の両方でオンになっています。  <br/> そのため、認証サーバーは Azure AD です。  <br/> |多要素認証 (MFA)、クライアント-証明書ベース認証 (CBA)、条件付きアクセス (CA)、モバイルアプリケーション管理 (MAM) (Intune)。 \*  <br/> |
|オンプレミスのみ  <br/> |![MA トポロジでサポートされている SFB、オンプレミスのみ。](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)ユーザーの所属/メールボックスの場所: オンプレミス  <br/> |MA がオンプレミスの SFB に対してオンになっています。  <br/> そのため、認証サーバーは ADFS です。  <br/> 構成の詳細については、[この記事](https://technet.microsoft.com/library/mt710548.aspx)を参照してください。 <br/> |MFA (Windows デスクトップのみ-モバイルクライアントはサポートされていません)。 Exchange 統合の機能はありません。  <br/><p> **この方法はお勧めしません。こちらを参照してください。**[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)<p/> |
   
> [!IMPORTANT]
> 音声ガイダンスの数を減らすには、Skype for Business と Exchange (およびそれらのオンライン対応) の間で、MA の状態を同じにすることをお勧めします。 
  
混在トポロジでは、SFB の分割ドメインハイブリッドの組み合わせが関係しています。 現在サポートされている混在トポロジを次に示します。
  
|トポロジ名  <br/> |例  <br/> |説明  <br/> |サポートされている  <br/> |
|:-----|:-----|:-----|:-----|
|混在1  <br/> |![MA のトポロジでサポートされている SFB、混合 1 (EXO + SFB)。](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> ユーザーの所属/メールボックスの場所: EXO および SFB  <br/> |MA は SFB に対して有効になっていません。このトポロジでは、SFB MA 機能は利用できません。  <br/> |SFB の MA 機能はありません。  <br/> |
|混合2  <br/> |![S4B 混在トポロジ2、SFBO、MA が EXCH on on-premises を使用してサポートされている MA。](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> ユーザーの所属/メールボックスの場所: EXCH および SFBO  <br/> |MA は SFBO に対してのみオンになっています。 承認サーバーは、SFBO に所属するユーザーの Azure AD ですが、EXCH オンプレミスで AD を使用します。  <br/> |Intune を使用した MFA、CBA、CA/MAM。\*  <br/> |
|混在3  <br/> |![SFB を使用した MA、MA がオンの EXO、さらに EXCH と SFB on on-premises がサポートされています。](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> ユーザーの所属/メールボックスの場所: EXO + SFB、または EXCH + SFB  <br/> |このトポロジで使用できる SFB MA 機能はありません  <br/> |SFB の MA 機能はありません。  <br/> |
|混在4  <br/> |![SFB でサポートされている MA、MA on の SFBO、および EXCH と SFB。](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> ユーザーの所属/メールボックスの場所: EXCH + SFBO または EXCH + SFB  <br/> |MA は SFBO に対してオンになっているため、認証サーバーは SFBO に所属するユーザーの Azure AD です。 SFB および EXO のオンプレミスのユーザーは AD を使用します。  <br/> |オンラインユーザーのみを対象とした、MFA、CBA、Intune での CA/MAM。\*  <br/> |
|混在5  <br/> |![SFB でサポートされている MA、MA を使用した EXO、および MA での SFBO、および EXCH と SFB on on-premises。](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> ユーザーの所属/メールボックスの場所: EXO + SFBO、EXO + SFB、EXCH + SFBO、または EXCH + SFB  <br/> |MA は EXO と SFBO の両方でオンになっているため、認証サーバーは SFBO に所属するユーザーの Azure AD です。EXCH のオンプレミスユーザーと SFB AD を使用します。  <br/> |オンラインユーザーのみを対象とした、MFA、CBA、Intune での CA/MAM。\*  <br/> |
|6つ混在  <br/> |![6を混在させたトポロジでは、先進認証は4つのすべての possibile の場所でオンになっています。これは、最適なおいの場合です。](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> ユーザーの所属/メールボックスの場所: EXO + SFBO、EXO + SFB、EXCH + SFBO、または EXCH + SFB  <br/> |MA はすべてのユーザーに対して Azure AD を使用します。 (オンラインとオンプレミス)  <br/>  展開の[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)手順については、「」を参照してください。 <br/> |すべてのユーザーの MFA、CBA、および CA/MAM (Intune 経由)。  <br/> |
   
\*-MFA には、Windows デスクトップ、MAC、iOS、Android デバイス、および Windows Phone が含まれます。CBA には、Windows デスクトップ、iOS、Android デバイスが含まれています。Intune を使用した CA/MAM。 Android および iOS デバイスを含みます。 
  
> [!IMPORTANT]
> 多くの場合、ユーザーが**複数の音声ガイダンス**を表示することがありますが、場合によっては、混合トポロジのすべてのバージョンの場合と同様に、クライアントが必要とするすべてのサーバーリソースで MA の状態が同じではないことに注意する必要があります。

> [!IMPORTANT]
> また、場合によっては (特に混合1、3、および 5)、 [AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online)レジストリキーが Windows デスクトップクライアントの適切な構成のために設定されている必要があることにも注意してください。
  

