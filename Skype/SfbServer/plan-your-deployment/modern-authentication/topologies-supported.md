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
description: この記事では、Skype for Business のモダン認証でサポートされるオンライン トポロジとオンプレミス トポロジ、および各トポロジに適用されるセキュリティ機能について説明します。
ms.openlocfilehash: 6bc61f8517200ffc7de4b836caabdbafe547929a2a947b4acb62821941f5bdc5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54352635"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>先進認証でサポートされている Skype for Business トポロジ

この記事では、Skype for Business のモダン認証でサポートされるオンライン トポロジとオンプレミス トポロジ、および各トポロジに適用されるセキュリティ機能について説明します。

## <a name="modern-authentication-in-skype-for-business"></a>最新の認証 (Skype for Business

Skype for Business認証のセキュリティ上の利点を活用できます。 Skype for Businessは Exchange と密接に動作しますので、Skype for Business クライアント ユーザーに表示されるログイン動作も、Exchange の MA 状態の影響を受Exchange。 これは、分割ドメイン ハイブリッドがSkype for Business場合にも適用されます。 これは多くの可動部分ですが、ここでの目的は、サポートされているトポロジのリストを簡単に視覚化できます。

オンラインSkype for Business、Skype for Business、Exchange Server、Exchange、オンラインでサポートされているトポロジMA。

<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. -->

### <a name="supported-ma-topologies-in-skype-for-business"></a>MAでサポートされているトポロジSkype for Business

2 つのサーバー アプリケーションと、Microsoft 365 または Office 365 ワークロードが 2 つSkype for Business可能性があります。MA。

- Skype for Business (CU 5) オンプレミス

- Skype for Business (SFBO)

- Exchangeオンプレミスのサーバー

- Exchange サーバー オンライン (EXO)

認証のもう 1 MA重要な部分は、ユーザーの認証 (authN) と承認 (authZ) の場所を知ることです。 2 つのオプションは次のとおりです。

- Azure AD Microsoft Cloud のオンライン

- Active Directory フェデレーション サーバー (ADFS) オンプレミス

そのため、Azure AD を使用したクラウドの EXO と SFBO、および Exchange Server (EXCH) と Skype for Business サーバー (SFB) オンプレムを使用して、少し次のように見えます。

![MA をオンにするときに関係する可能性があるすべてのアプリケーション (Exchange および Skype for Business) とワークロード (EXO と SFBO)、および両方の承認サーバー (ADFS と evoSTS) の例です。](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)

サポートされているトポロジを次に示します。 グラフィックスのキーに注意してください。

- アイコンが淡色または灰色の場合、シナリオでは使用されません。

- EXO はExchange Online。

- SFBO はオンラインSkype for Businessです。

- EXCH はExchangeで使用されます。

- SFB はSkype for Businessで使用されます。

- 承認サーバーは三角形で表されます。たとえば、Azure ADは、その背後にクラウドを持つ三角形です。

- 矢印は、クライアントが指定されたサーバー リソースに到達しようとするときに使用される承認サーバーを指します。

最初に、オンプレミス専用MA Skype for Businessクラウド専用トポロジの両方について説明します。

> [!IMPORTANT]
> オンラインでモダン認証をセットアップするSkype for Businessですか? この機能を有効にする手順は次 [のとおりです](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。

|トポロジ名  <br/> |例  <br/> |説明  <br/> |サポート  <br/> |
|:-----|:-----|:-----|:-----|
|クラウドのみ  <br/> |![サポートされる SFB は、MAクラウドでのみサポートされます。](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)ユーザーホーム/メールボックスの場所: Online  <br/> |MA EXO と SFBO の両方に対してオンです。  <br/> したがって、承認サーバーは Azure AD。  <br/> |多要素認証 (MFA)、クライアント証明書ベース認証 (CBA)、条件付きアクセス (CA)/モバイル アプリケーション管理 (MAM) (Intune) \*  <br/> |
|On-prem のみ  <br/> |![サポートされている SFB MAトポロジでのみサポートされます。](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)ユーザーホーム/メールボックスの場所: オンプレミス  <br/> |MA SFB オンプレミスの場合はオンです。  <br/> したがって、承認サーバーは ADFS です。  <br/> 構成の詳細については、この記事を [参照してください。](/microsoft-365/enterprise/hybrid-modern-auth-overview) <br/> |MFA (Windowsデスクトップのみ - モバイル クライアントはサポートされていません)。 統合Exchange機能はありません。  <br/><p> **この方法はお勧めしません。こちらを参照してください。**[https://aka.ms/ModernAuthOverview](/microsoft-365/enterprise/hybrid-modern-auth-overview)<p/> |

> [!IMPORTANT]
> プロンプトの数を減MA、Skype for Business と Exchange (およびオンライン対応) の間で、MA 状態を同じにするようお勧めします。

混在トポロジには、SFB 分割ドメイン ハイブリッドの組み合わせが含まれる。 現在サポートされている混在トポロジを次に示します。

|トポロジ名  <br/> |例  <br/> |説明  <br/> |サポート  <br/> |
|:-----|:-----|:-----|:-----|
|混合 1  <br/> |![サポートされている SFB は、MAミックス 1 (EXO + SFB) でサポートされています。](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> ユーザーホーム/メールボックス: EXO と SFB  <br/> |MA SFB が有効になっていません。このトポロジでMA SFB の機能はありません。  <br/> |SFB MA機能はありません。  <br/> |
|混合 2  <br/> |![S4B MAトポロジ 2、SFBO、および EXCH on-prem MAを使用してサポートされています。](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> ユーザーホーム/メールボックス: EXCH と SFBO  <br/> |MA SFBO でのみオンです。 承認サーバーは、SFBO ADが EXCH オンプレミスのユーザー AD Azure サーバーです。  <br/> |MFA、CBA、CA/MAM と Intune。\*  <br/> |
|混合 3  <br/> |![SFB MA EXO をオンにした場合MA EXCH と SFB がオンプレミスでサポートされています。](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> ユーザーホーム/メールボックス: EXO + SFB、または EXCH + SFB  <br/> |このトポロジMA SFB の機能はありません  <br/> |SFB MA機能はありません。  <br/> |
|混合 4  <br/> |![SFB MA SFBO がオンの場合MA EXCH と SFB でサポートされています。](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> ユーザーホーム/メールボックス: EXCH +SFBO または EXCH + SFB  <br/> |MA SFBO に対して有効であるため、承認サーバーは SFBO にAD Azure サーバーです。 SFB および EXO のプレム ユーザーは、このAD。  <br/> |MFA、CBA、CA/MAM と Intune のオンライン ユーザーのみ。\*  <br/> |
|混合 5  <br/> |![SFB MA EXO と MA、およびオンプレミスの EXCH と SFB MAサポートされています。](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> ユーザーホーム/メールボックス: EXO + SFBO、EXO + SFB、EXCH + SFBO、または EXCH + SFB  <br/> |MA EXO と SFBO の両方でオンであるため、承認サーバーは SFBO にAD Azure サーバーです。EXCH および SFB の on-prem ユーザーは、AD。  <br/> |MFA、CBA、CA/MAM と Intune のオンライン ユーザーのみ。\*  <br/> |
|混合 6  <br/> |![Mixed 6 トポロジでは、モダン認証は 4 つの possibile の場所すべてで有効です。モダン認証に関しては理想的なサイト化です。](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> ユーザーホーム/メールボックス: EXO + SFBO、EXO + SFB、EXCH + SFBO、または EXCH + SFB  <br/> |MAはどこにでもあるので、認証サーバーは、すべてのユーザー AD Azure サーバーです。 (オンラインおよびオンプレミス)  <br/>  展開手順 [https://aka.ms/ModernAuthOverview](/microsoft-365/enterprise/hybrid-modern-auth-overview) については、「」を参照してください。 <br/> |すべてのユーザーの MFA、CBA、CA/MAM (Intune 経由)。  <br/> |

\*- MFA には、Windowsデスクトップ、MAC、iOS、Android デバイス、Windowsが含まれます。CBA には、Windows、iOS、Android デバイスが含まれます。Intune の CA/MAM には、Android デバイスと iOS デバイスが含まれます。

> [!IMPORTANT]
> ユーザーが複数のプロンプトを表示する場合があります。特に、MA 状態が、すべてのバージョンの Mixed トポロジと同様に、クライアントが必要と要求する可能性のあるすべてのサーバー リソースで同じではない場合に注意することが非常に重要です。

> [!IMPORTANT]
> また、場合によっては (1、3、5 の混在) [AllowADALForNonLyncIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online)レジストリ キーを設定して、Windows デスクトップ クライアントの適切な構成を行う必要があります。