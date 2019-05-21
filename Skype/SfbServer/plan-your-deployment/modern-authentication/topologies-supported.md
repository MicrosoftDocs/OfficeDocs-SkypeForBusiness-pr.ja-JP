---
title: 先進認証でサポートされる Skype for Business トポロジ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: この記事では、どのオンラインおよびオンプレミス トポロジが Skype for Business での先進認証でサポートされるかを、各トポロジに適用されるセキュリティ機能とともに一覧表示します。
ms.openlocfilehash: 04dc6933fb63db7ebaec4f2c346e3cfbc60f9e24
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297338"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>Skype for Business topologies supported with Modern Authentication
 
この記事では、どのオンラインおよびオンプレミス トポロジが Skype for Business での先進認証でサポートされるかを、各トポロジに適用されるセキュリティ機能とともに一覧表示します。
  
## <a name="modern-authentication-in-skype-for-business"></a>Skype for Business での先進認証

Skype for Business は先進認証のセキュリティ上の長所を活用します。Skype for Business は Exchange と密接に動作するため、Skype for Business クライアントのユーザーに表示されるログイン動作は、MA status of Exchange の MA の状態による影響も受けます。これは、Skype for Business の分割ドメイン ハイブリッドを利用している場合にも適用されます。これは動きのある部分が多いですが、ここでの目的としてはサポートされるトポロジを簡単に見ることができる一覧を提供することです。
  
Skype for Business、Skype for Business Online、Exchange Server、Exchange Online の場合に、どのトポロジが MA でサポートされますか?
  
<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. --> 
  
### <a name="supported-ma-topologies-in-skype-for-business"></a>Skype for Business でサポートされる MA トポロジ

2 つのサーバー アプリケーション、MA によって使用される Skype for Business トポロジを含む、2 つの Office 365 ワークロードで構成される可能性があります。
  
- Skype for Business server (CU 5) オンプレミス
    
- Skype for Business Online (SFBO)
    
- Exchange Server オンプレミス
    
- Exchange Server Online (EXO)
    
MA のもう 1 つの重要な部分は、ユーザーの認証 (authN) と承認 (authZ) がどこで発生するかを理解していることです。次の 2 つのオプションがあります。
  
- Azure AD、Microsoft Cloud でオンライン
    
- Active Directory フェデレーション サーバー (ADFS) オンプレミス
    
このように、Azure AD のクラウドでは、EXO と SFBO と、Exchange Server (EXCH)、Skype for Business server (SFB) オンプレミスというようになります。
  
![すべてのアプリケーション (Exchange および Skype for Business) とワークロード (EXO および SFBO)、および MA をオンにするときに関与させられる両方の認証サーバー (ADFS および evoSTS) の例。](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)
  
サポートされるトポロジを以下に示します。これらの図では、次の重要な点に注意してください。
  
- 薄い、またはグレー表示のアイコンは、シナリオで使用されていません。
    
- EXO は Exchange Online です。
    
- SFBO は Skype for Business Online です。
    
- EXCH は Exchange オンプレミスです。
    
- SFB は Skype for Business オンプレミスです。
    
- 認証サーバーは三角形で表されます。たとえば、Azure AD は後ろに雲マークが付いた三角形になります。
    
- 矢印は、クライアントが指定されたサーバー リソースに到達しようと試みるときに使用する認証サーバーを指します。
    
最初に、オンプレミスのみ、クラウドのみの両方のトポロジの Skype for Business での MA について見ていきましょう。
  
> [!IMPORTANT]
> Skype for Business Online で先進認証を設定する準備ができましたか? この機能を有効にする手順は[次](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)のとおりです。 
  
|トポロジの名前  <br/> |例  <br/> |説明  <br/> |サポート対象  <br/> |
|:-----|:-----|:-----|:-----|
|クラウドのみ  <br/> |![MA トポロジのある SFB をサポート (クラウド限定)。](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)ユーザーの所属/メールボックスの場所: オンライン   <br/> |MA は EXO と SFBO の両方でオンです。  <br/> このため、認証サーバーは Azure AD です。  <br/> |多要素認証 (MFA)、クライアント証明書を使用した認証 (CBA)、Intune での条件付きアクセス (CA)/モバイル アプリケーション管理 (MAM)。 \*  <br/> |
|オンプレミスのみ  <br/> |![MA トポロジがある SFB をサポート (オンプレミス限定)。](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)ユーザーの所属/メールボックスの場所: オンプレミス  <br/> |MA が SFB オンプレミスでオンになります。  <br/> このため、認証サーバーは ADFS です。  <br/> 構成の詳細については、[この記事](https://technet.microsoft.com/en-us/library/mt710548.aspx)を参照してください。 <br/> |MFA (Windows デスクトップのみ。モバイル クライアントはサポートされません)。Exchange 統合の機能はサポート対象外です。  <br/> |
   
> [!IMPORTANT]
> プロンプトの数を減らせるように、Skype for Business と Exchange (およびその他のオンライン上の同等製品) にわたり MA の状態が同じであることを推奨します。 
  
混合トポロジでは、SFB 分割ドメインのハイブリッドの組み合わせが含まれます。現在サポートされている混合トポロジを以下に示します。
  
|トポロジの名前  <br/> |例  <br/> |説明  <br/> |サポート対象  <br/> |
|:-----|:-----|:-----|:-----|
|混合 1  <br/> |![混合型 1 (EXO + SFB) の MA トポロジのある SFB をサポート。](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> ユーザーの所属/メールボックスの場所: EXO および SFB  <br/> |MA は SFB で有効ではありません。このトポロジで利用できる SFB の MA 機能はありません。  <br/> |SFB の MA 機能はサポート対象外です。  <br/> |
|混合 2  <br/> |![SFBO にオンプレミスの EXCH と連動する MA が加わった S4B 混合型トポロジ 2 のある MA をサポート。](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> ユーザーの所属/メールボックスの場所: EXCH および SFB  <br/> |MA は SFBO のみでオンになります。 承認サーバーは、SFBO のホームユーザーであるが、オンプレミスの広告の EXCH に Azure AD を使用します。  <br/> |[Intune] で MFA、CBA、CA/MAM。\*  <br/> |
|混合 3  <br/> |![SFB がある MA、MA がオンの EXO、さらに EXCH とオンプレミスの SFB をサポート。](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> ユーザーの所属/メールボックスの場所: EXO + SFB または EXCH + SFB  <br/> |このトポロジでは利用できる SFB の MA 機能はありません  <br/> |SFB の MA 機能はサポート対象外です。  <br/> |
|混合 4  <br/> |![SFB がある MA、MA がオンの SFBO、さらに EXCH と SFB をサポート。](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> ユーザーの所属/メールボックスの場所: EXCH + SFBO または EXCH + SFB  <br/> |MA は SFBO に対応しているため、承認サーバーは、SFBO で構成されているユーザー用の Azure AD です。 SFB と EXO のオンプレミスユーザーは、AD を使用します。  <br/> |オンラインユーザーのみを対象とした Intune での MFA、CBA、CA/MAM。\*  <br/> |
|混合 5  <br/> |![SFB の MA、MA がオンの EXO、MA がある SFBO、さらに EXCH とオンプレミスの SFB をサポート。](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> ユーザーの所属/メールボックスの場所: EXO + SFBO、EXO + SFB、EXCH + SFBO、または EXCH + SFB  <br/> |MA は EXO と SFBO の両方でオンになっているため、承認サーバーは、SFBO に所属するユーザー用の Azure AD です。EXCH および SFB のオンプレミスユーザーは、広告を使用します。  <br/> |オンラインユーザーのみを対象とした Intune での MFA、CBA、CA/MAM。\*  <br/> |
|複合6  <br/> |![Mixed 6 トポロジでは、先進認証は 4 つの可能な場所すべてにおいてオンになります。先進認証の場合には、理想的な状況です。](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> ユーザーの所属/メールボックスの場所: EXO + SFBO、EXO + SFB、EXCH + SFBO、または EXCH + SFB  <br/> |MA はどこにいても、承認サーバーはすべてのユーザーに対して Azure AD です。 (オンラインとオンプレミス)  <br/>  展開の[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)手順については、こちらを参照してください。 <br/> |すべてのユーザーに対する MFA、CBA、CA/MAM (Intune 経由)。  <br/> |
   
\*-MFA には、Windows デスクトップ、MAC、iOS、Android デバイス、Windows Phone が含まれます。CBA には、Windows デスクトップ、iOS、Android デバイスが含まれています。Android および iOS デバイスを含む、Intune との CA/MAM。 
  
> [!IMPORTANT]
> 一部の場合において、ユーザーに対して**複数のプロンプト**が表示される可能性があることに注意してください。これは特に、すべてのバージョンの混合トポロジでの場合と同様に、クライアントで必要され要求されるすべてのサーバー リソースにわたり MA の状態が同じではない場合に発生します。 

> [!IMPORTANT]
> また、場合によっては、Windows デスクトップクライアントの適切な構成を行うために[AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/en-us/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online)レジストリキーを設定する必要があることにも注意してください。
  

