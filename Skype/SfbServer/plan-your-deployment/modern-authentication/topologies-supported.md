---
title: 先進認証でサポートされている Skype for Business トポロジ
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
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: この記事では、Skype for Business のモダン認証でサポートされるオンラインおよびオンプレミスのトポロジと、各トポロジに適用されるセキュリティ機能を示します。
ms.openlocfilehash: b7582b6f77a3286a2b245b4b390efee7bbef62c1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810107"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>先進認証でサポートされている Skype for Business トポロジ

この記事では、Skype for Business のモダン認証でサポートされるオンラインおよびオンプレミスのトポロジと、各トポロジに適用されるセキュリティ機能について説明します。

## <a name="modern-authentication-in-skype-for-business"></a>Skype for Business でのモダン認証

Skype for Business では、最新の認証のセキュリティ上の利点を活用できます。 Skype for Business は Exchange と密接に動作します。このため、Skype for Business クライアントユーザーに表示されるログイン動作は、Exchange のMA影響を受ける可能性があります。 これは、Skype for Business の分割ドメイン ハイブリッドがある場合にも適用されます。 これは多くの移動部分ですが、ここでの目的は、サポートされているトポロジの一覧を簡単に視覚化する方法です。

Skype for Business、Skype for Business Online、Exchange Server、および Exchange Online では、どのトポロジがサポートMA。

<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. -->

### <a name="supported-ma-topologies-in-skype-for-business"></a>Skype for Business MAサポートされるトポロジ

2 つのサーバー アプリケーションと、2 つの Microsoft 365 または Office 365 ワークロードが、MA で使用される Skype for Business トポロジに関係する可能性があります。

- オンプレミスの Skype for Business サーバー (CU 5)

- Skype for Business Online (SFBO)

- オンプレミスの Exchange サーバー

- Exchange サーバー オンライン (EXO)

認証のもう 1 MA重要な部分は、ユーザーの認証 (authN) と承認 (authZ) がどこで実行されるのかを知ることです。 次の 2 つのオプションがあります。

- Azure AD Microsoft Cloud のオンライン

- Active Directory フェデレーション サーバー (ADFS) オンプレミス

Azure AD を使用したクラウドの EXO と SFBO、および Exchange Server (EXCH) と Skype for Business サーバー (SFB) をオンプレマに使用すると、少し次のように表示されます。

![MA をオンにするときに関係する可能性があるすべてのアプリケーション (Exchange と Skype for Business) とワークロード (EXO および SFBO)、および両方の認証サーバー (ADFS と evoSTS) の例。](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)

サポートされているトポロジを次に示します。 グラフィックスのキーに注意してください。

- アイコンが淡色または灰色の場合、シナリオでは使用されません。

- EXO は Exchange Online です。

- SFBO は Skype for Business Online です。

- EXCH は Exchange オンプレミスです。

- SFB は Skype for Business オンプレミスです。

- 承認サーバーは三角形で表されます。たとえば、Azure ADは、その背後にクラウドがある三角形です。

- 矢印は、クライアントが指定されたサーバー リソースに到達しようとするときに使用される承認サーバーを指します。

最初に、オンプレミスMAまたはクラウド専用の両方のトポロジで Skype for Business を使用する方法について説明します。

> [!IMPORTANT]
> Skype for Business Online でモダン認証をセットアップする準備はできましたか? この機能を有効にする手順は次 [のとおりです](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。

|トポロジ名  <br/> |例  <br/> |説明  <br/> |サポート  <br/> |
|:-----|:-----|:-----|:-----|
|クラウドのみ  <br/> |![サポートされている SFB (MA トポロジ、クラウドのみ)。](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)ユーザーの自宅/メールボックスの場所: オンライン  <br/> |MA EXO と SFBO の両方でオンです。  <br/> したがって、認証サーバーは Azure AD。  <br/> |多要素認証 (MFA)、クライアント証明書ベース認証 (CBA)、Intune による条件付きアクセス (CA)/モバイル アプリケーション管理 (MAM)。 \*  <br/> |
|オンプレムのみ  <br/> |![サポートされている SFB とMAトポロジ (オンプレミスのみ)。](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)ユーザーの自宅/メールボックスの場所: オンプレミス  <br/> |MA SFB オンプレミスでオンです。  <br/> したがって、認証サーバーは ADFS です。  <br/> 構成の詳細については、この記事を [参照してください。](https://technet.microsoft.com/library/mt710548.aspx) <br/> |MFA (Windows デスクトップのみ - モバイル クライアントはサポートされていません)。 Exchange 統合機能はありません。  <br/><p> **この方法はお勧めしません。こちらをご覧ください。**[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)<p/> |

> [!IMPORTANT]
> プロンプトの数を減MA、Skype for Business と Exchange (および対応するオンライン) の間で同じ状態に設定するようお勧めします。

混在トポロジには、SFB 分割ドメイン ハイブリッドの組み合わせが含まれる。 現在サポートされている混在トポロジは次のとおりです。

|トポロジ名  <br/> |例  <br/> |説明  <br/> |サポート  <br/> |
|:-----|:-----|:-----|:-----|
|混合 1  <br/> |![混合 1 (EXO + SFB) MAサポートされている SFB。](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> ユーザーの自宅/メールボックスの場所: EXO および SFB  <br/> |MA SFB が有効になっていません。このトポロジでMA SFB の機能はありません。  <br/> |SFB MA機能はありません。  <br/> |
|混合 2  <br/> |![S4B MA 2、SFBO、および EXCH on-prem MAで動作する場合にサポートされます。](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> ユーザーの自宅/メールボックスの場所: EXCH および SFBO  <br/> |MA SFBO でのみオンです。 認証サーバーは SFBO ADユーザーの Azure 認証ですが、exCH ADには使用できません。  <br/> |MFA、CBA、INTUNE を使用した CA/MAM。\*  <br/> |
|混合 3  <br/> |![SFB MA EXO、およびオンプレミスの EXCH MA SFB でサポートされます。](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> ユーザーの自宅/メールボックスの場所: EXO + SFB、または EXCH + SFB  <br/> |このトポロジMA SFB の機能はありません。  <br/> |SFB MA機能はありません。  <br/> |
|混合 4  <br/> |![SFB MA SFBO、および EXCH MA SFB でサポートされます。](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> ユーザーの自宅/メールボックス: EXCH +SFBO または EXCH + SFB  <br/> |MA SFBO に対して有効であるため、SFBO にADの Azure 認証サーバーです。 SFB および EXO のオンプレマ ユーザーは、このAD。  <br/> |MFA、CBA、オンライン ユーザー向け Intune を使用した CA/MAM。\*  <br/> |
|混合 5  <br/> |![SFB MA EXO と MA および SFBO MA EXCH および SFB オンプレミスでサポートされます。](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> ユーザーの自宅/メールボックス: EXO + SFBO、EXO + SFB、EXCH + SFBO、または EXCH + SFB  <br/> |MA EXO と SFBO の両方でオンであるため、認証サーバーは SFBO にADの Azure 認証サーバーです。EXCH および SFB のオンプレマ ユーザーは、このAD。  <br/> |MFA、CBA、オンライン ユーザー向け Intune を使用した CA/MAM。\*  <br/> |
|混合 6  <br/> |![Mixed 6 トポロジでは、モダン認証は 4 つの場所すべてで有効です。モダン認証に関しては理想的な方法です。](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> ユーザーの自宅/メールボックス: EXO + SFBO、EXO + SFB、EXCH + SFBO、または EXCH + SFB  <br/> |MAすべての場所にあるため、認証サーバーは Azure ADすべてのユーザーに提供されます。 (オンラインとオンプレミス)  <br/>  展開手順 [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) については、以下を参照してください。 <br/> |すべてのユーザーの MFA、CBA、CA/MAM (Intune 経由)。  <br/> |

\* - MFA には、Windows デスクトップ、MAC、iOS、Android デバイス、Windows Phone が含まれます。CBA には、Windows デスクトップ、iOS、Android デバイスが含まれます。Intune を使用した CA/MAM には、Android デバイスと iOS デバイスが含まれます。

> [!IMPORTANT]
> すべてのバージョンの混在トポロジの場合のように、ユーザーに複数のプロンプトが表示される場合があります。特に、クライアントが必要と要求する可能性のあるすべてのサーバー リソースで MA の状態が同じではない場合があります。

> [!IMPORTANT]
> また、Windows デスクトップ クライアントの適切な構成のために [AllowADALForNonLyncIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) レジストリ キーを設定する必要がある場合もあります (1、3、および 5 が混在しています)。


