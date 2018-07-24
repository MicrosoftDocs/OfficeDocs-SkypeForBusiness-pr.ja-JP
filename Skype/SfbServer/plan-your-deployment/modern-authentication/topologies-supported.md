---
title: 先進認証でサポートされる Skype for Business トポロジ
ms.author: tracyp
author: MSFTTracyP
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: この記事では、どのオンラインおよびオンプレミス トポロジが Skype for Business での先進認証でサポートされるかを、各トポロジに適用されるセキュリティ機能とともに一覧表示します。
ms.openlocfilehash: cc849dc1df0f4bf97bb362449ef1ded58596cb91
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21001800"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>先進認証でサポートされる Skype for Business トポロジ
 
この記事では、どのオンラインおよびオンプレミス トポロジが Skype for Business での先進認証でサポートされるかを、各トポロジに適用されるセキュリティ機能とともに一覧表示します。
  
## <a name="modern-authentication-in-skype-for-business"></a>Skype for Business での先進認証

Skype for Business は先進認証のセキュリティ上の長所を活用します。Skype for Business は Exchange と密接に動作するため、Skype for Business クライアントのユーザーに表示されるログイン動作は、MA status of Exchange の MA の状態による影響も受けます。これは、Skype for Business の分割ドメイン ハイブリッドを利用している場合にも適用されます。これは動きのある部分が多いですが、ここでの目的としてはサポートされるトポロジを簡単に見ることができる一覧を提供することです。
  
Skype for Business、Skype for Business Online、Exchange Server、Exchange Online の場合に、どのトポロジが MA でサポートされますか?
  
<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. --> 
  
### <a name="supported-ma-topologies-in-skype-for-business"></a>Skype for Business でサポートされる MA トポロジ

2 つのサーバー アプリケーション、MA によって使用される Skype for Business トポロジを含む、2 つの Office 365 ワークロードで構成される可能性があります。
  
- Skype ビジネス サーバー (CU 5) 設置
    
- Skype for Business Online (SFBO)
    
- Exchange Server オンプレミス
    
- Exchange Server Online (EXO)
    
MA のもう 1 つの重要な部分は、ユーザーの認証 (authN) と承認 (authZ) がどこで発生するかを理解していることです。次の 2 つのオプションがあります。
  
- Azure AD、Microsoft Cloud でオンライン
    
- Active Directory フェデレーション サーバー (ADFS) オンプレミス
    
EXO と SFBO と Azure AD は、雲の中で、次のようになる少しようと Exchange Server (EXCH) およびビジネス サーバー (デバイス) の prem. 上の Skype
  
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
> Skype for Business Online での先進認証をセットアップする準備が整いましたら、 この機能を有効にする手順は[ここで](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。 
  
|トポロジの名前  <br/> |例  <br/> |説明  <br/> |サポート対象  <br/> |
|:-----|:-----|:-----|:-----|
|クラウドのみ  <br/> |![MA トポロジのある SFB をサポート (クラウド限定)。](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)ユーザーの所属/メールボックスの場所: オンライン   <br/> |MA は EXO と SFBO の両方でオンです。  <br/> このため、認証サーバーは Azure AD です。  <br/> |多要素認証 (MFA) では、クライアント証明書ベースの認証 (同行)、条件付きアクセス (CA)/Intune のように、モバイル アプリケーションの管理 (MAM)。 \*  <br/> |
|オンプレミスのみ  <br/> |![MA トポロジがある SFB をサポート (オンプレミス限定)。](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)ユーザーの所属/メールボックスの場所: オンプレミス  <br/> |MA が SFB オンプレミスでオンになります。  <br/> このため、認証サーバーは ADFS です。  <br/> 構成の詳細についてを参照してください[この記事](https://technet.microsoft.com/en-us/library/mt710548.aspx)。 <br/> |MFA (Windows デスクトップのみ。モバイル クライアントはサポートされません)。Exchange 統合の機能はサポート対象外です。  <br/> |
   
> [!IMPORTANT]
> プロンプトの数を減らせるように、Skype for Business と Exchange (およびその他のオンライン上の同等製品) にわたり MA の状態が同じであることを推奨します。 
  
混合トポロジでは、SFB 分割ドメインのハイブリッドの組み合わせが含まれます。現在サポートされている混合トポロジを以下に示します。
  
|トポロジの名前  <br/> |例  <br/> |説明  <br/> |サポート対象  <br/> |
|:-----|:-----|:-----|:-----|
|混合 1  <br/> |![混合型 1 (EXO + SFB) の MA トポロジのある SFB をサポート。](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> ユーザーの所属/メールボックスの場所: EXO および SFB  <br/> |MA は SFB で有効ではありません。このトポロジで利用できる SFB の MA 機能はありません。  <br/> |SFB の MA 機能はサポート対象外です。  <br/> |
|混合 2  <br/> |![SFBO にオンプレミスの EXCH と連動する MA が加わった S4B 混合型トポロジ 2 のある MA をサポート。](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> ユーザーの所属/メールボックスの場所: EXCH および SFB  <br/> |MA は SFBO のみです。 認証サーバーは Azure AD SFBO、EXCH オンプレミスの AD に置かれているユーザーです。  <br/> |MFA、同行では、CA/Intune で MAM です。\*  <br/> |
|混合 3  <br/> |![SFB がある MA、MA がオンの EXO、さらに EXCH とオンプレミスの SFB をサポート。](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> ユーザーの所属/メールボックスの場所: EXO + SFB または EXCH + SFB  <br/> |このトポロジでは利用できる SFB の MA 機能はありません  <br/> |SFB の MA 機能はサポート対象外です。  <br/> |
|混合 4  <br/> |![SFB がある MA、MA がオンの SFBO、さらに EXCH と SFB をサポート。](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> ユーザーの所属/メールボックスの場所: EXCH + SFBO または EXCH + SFB   <br/> |MA が SFBO のでは、そのため、認証サーバーは、Azure AD SFBO に置かれているユーザーのです。 デバイスと EXO prem のユーザーは、AD を使用します。  <br/> |MFA、同行では、CA/Intune オンラインのユーザーのみに MAM です。\*  <br/> |
|混合 5  <br/> |![SFB の MA、MA がオンの EXO、MA がある SFBO、さらに EXCH とオンプレミスの SFB をサポート。](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> ユーザーの所属/メールボックスの場所: EXO + SFBO、EXO + SFB、EXCH + SFBO、または EXCH + SFB  <br/> |MA は EXO と SFBO、したがって SFBO; に置かれているユーザーの認証サーバーは、Azure AD です。EXCH とデバイスの prem のユーザーは、AD を使用します。  <br/> |MFA、同行では、CA/Intune オンラインのユーザーのみに MAM です。\*  <br/> |
|混合 6  <br/> |![Mixed 6 トポロジでは、先進認証は 4 つの可能な場所すべてにおいてオンになります。先進認証の場合には、理想的な状況です。](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> ユーザーの所属/メールボックスの場所: EXO + SFBO、EXO + SFB、EXCH + SFBO、または EXCH + SFB  <br/> |MA は、すべての場所では、そのため、認証サーバーはすべてのユーザーは Azure AD。 (オンラインと設置型)  <br/>  参照してください[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)の展開手順を実行します。 <br/> |MFA、同行および CA と MAM (Intune) 経由ですべてのユーザー用です。  <br/> |
   
\*-MFA は、Windows デスクトップ、MAC、iOS、Android デバイス、および Windows の電話は含まれています。同行には、Windows デスクトップ、iOS および Android デバイスが含まれています。CA と MAM Intune とには、Android と iOS のデバイスが含まれています。 
  
> [!IMPORTANT]
> 一部の場合において、ユーザーに対して**複数のプロンプト**が表示される可能性があることに注意してください。これは特に、すべてのバージョンの混合トポロジでの場合と同様に、クライアントで必要され要求されるすべてのサーバー リソースにわたり MA の状態が同じではない場合に発生します。

> [!IMPORTANT]
> 場合によっては注意してください (具体的には混合し、1、3、5) [AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/en-us/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online)のレジストリ キーは、Windows デスクトップ クライアントの構成が適切に設定しなければなりません。
  

