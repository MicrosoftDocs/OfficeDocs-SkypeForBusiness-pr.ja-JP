---
title: ビジネス 2015年クライアント エクスペリエンスのユーザーのための Skype を計画します。
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: ': の概要については、新しい Skype のビジネスとオンライン ビジネス、ビジネス サーバー 2019 の Skype、Skype のビジネス サーバー 2015、Lync Server 2013 では、Skype を使用しているかどうか、更新プログラムのユーザー、お客様の環境を準備するための手順やLync Server 2010。'
ms.openlocfilehash: 351582e7a7619541d5401acfb46854f61c9e052d
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531168"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>ビジネス 2015年クライアント エクスペリエンスのユーザーのための Skype を計画します。
 
**の概要:** 新しい Skype はビジネスおよびビジネス サーバー 2015、Lync Server 2013 では、Lync Server のオンライン ビジネスの Skype、Skype のビジネス サーバー 2019、Skype を使用しているかどうか、更新プログラムのユーザー、お客様の環境を準備するための手順についてください。2010。
  
2015 年 4 月 14 日 Lync 2013 用の Office の更新プログラムには、ビジネス ユーザー ・ インタ フェースの新しい Skype が含まれています。 この更新プログラムでは、クライアントの外観と動作を制御し、Lync 2013 クライアント エクスペリエンスを保持またはビジネス クライアント エクスペリエンスの向上の Skype を使用するかどうかを選択できます。 ビジネス クライアント用の Skype は効果的に、Lync 2013 クライアントは置き換えられ、管理者は既存の Lync クライアントの経験とビジネス クライアント エクスペリエンスの新しい Skype との間を選択するための機能を追加しました。 この更新プログラムの詳細については、「[April 14, 2015 update for Lync 2013 (Skype for Business) (2015 年 4 月 14 日、Lync 2013 (Skype for Business) の更新プログラム) (KB2889923)](https://support.microsoft.com/en-us/kb/2889923/)」を参照してください。
  
2015 5 月 12 日のビジネス クライアント用の更新された Skype を含む Office から別の毎月更新されます。 4 月の更新は、5 月 12日の選択を適用していない多くのお客様は、Office 2013 の更新します。 このトピックの情報は、クライアントの更新に対する組織、環境、ユーザーの準備に役立ちます。 ユーザーおよびサポート チームが容易に移行できるように、このトピックの情報を使用して、ユーザーに対してどちらのクライアント エクスペリエンスを使用するかを決定し、組織でクライアント更新プログラムを展開する前に環境に変更を加えてください。
  
- [What client experience do you want for your users?](user-experience.md#clientexperience)
    
- [Skype for Business クライアント用に環境を準備する](user-experience.md#usinglync)
    
- [Resources to help you prepare your support teams and your end users for the update](user-experience.md#support)
    
> [!NOTE]
> Lync 2013 クライアント エクスペリエンスは、ビジネス 2016年のクライアント バージョン用には、Skype のオプションではありません。 Lync 2013 クライアントを使用するようにクライアント環境を構成する前に、クライアント バージョンを調べて、バージョンの先頭が 16 ではない (16.x.x.x などではない) ことを確認してください。 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>ユーザーに対して必要なクライアント エクスペリエンスは何ですか?
<a name="clientexperience"> </a>

ビジネス クライアント用の新しい Skype、どのクライアントの機能をユーザーが取得すると、Lync またはビジネス用の Skype のいずれかを制御できます。 既定のクライアントの動作は、かどうか、またはを使用して Lync Skype ビジネス設置型またはオンラインによって異なります。 ビジネス クライアント用の更新された Skype が発生するビジネス オンライン (Lync オンライン) に、現在、Office 365 用リソース、Office 365 のビジネス プレミアムまたは Office 2013 の Skype を使用する場合、Skype の外観に触発されたもの-既定のユーザー エクスペリエンスになります。 今日、Lync Server の設置型を使用している、Lync クライアント エクスペリエンスが既定値になります。
  
クライアント ポリシーを使用することにより、ユーザーにどちらのクライアント エクスペリエンスを提供するか設定できます。 クライアント ポリシーは、Lync またはビジネス用の Skype にログインするとユーザーに適用される構成設定のセットです。
  
### <a name="skype-for-business-client-experience"></a>Skype for Business クライアント エクスペリエンス

Lync のすべての機能、に加えては、ビジネス用の Skype は、Skype から簡略化されたコントロールと一般的なアイコンでの新機能を提供します。 ビジネス用の Skype の新機能は、クライアントの機能をビジネスの新しい Skype のみ用意されています。 ビジネス用の Skype の新機能に関する詳細については、[ビジネス用の Skype の検出](https://go.microsoft.com/fwlink/p/?LinkId=528686)を参照してください。
  
### <a name="lync-client-experience"></a>Lync クライアント エクスペリエンス

Lync クライアント エクスペリエンスは、多くのユーザーが既に使いなれている Lync 2013 のクライアント エクスペリエンスによく似ていますが、いくつかの変更点についてユーザーに知らせておく必要があります。 Lync クライアント エクスペリエンスと Lync 2013 クライアントの違いについては、「[Lync を使っているときに Skype for Business が表示されるのはなぜですか?](https://go.microsoft.com/fwlink/p/?LinkId=544712)」と、このトピックの後方に追記されているリンク先を参照してください。
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Skype for Business クライアント用に環境を準備する
<a name="usinglync"> </a>

クライアントの更新に向けて環境を準備するのに必要な作業はそれほど多くありません。 クライアント エクスペリエンスを構成するのには何も変更を開始する前にビジネスのサーバーまたはクライアントのポリシー設定をサポートしている Lync Server のバージョンの Skype を使用しているかどうかを確認する必要があります。
  
ビジネス サーバーまたはクライアント エクスペリエンスを制御するポリシーの設定をサポートしている Lync Server のバージョンの Skype を使っていることを確認して、環境内でポリシー設定を構成する必要があります。 ビジネス サーバー、または使用する場合は、Lync Server の Skype のバージョンで、特定の手順を実行する必要に依存しているし、ユーザーは、設置するかどうかまたはオンラインです。 
  
ビジネス クライアント用の Skype を起動する最初の時間からのクライアント エクスペリエンスを制御することができますように、ユーザーにクライアント用更新プログラムが配信される前に、これらの変更を実行します。 次の表には、ユーザーのために必要なクライアント操作の環境を構成するために必要な手順へのリンクがあります。
  
|**Deployment**|**Skype for Business クライアント エクスペリエンス**|**Lync クライアント エクスペリエンス**|
|:-----|:-----|:-----|
|Skype for Business Online  <br/> |クライアント ビルド 4711.1002 (2015 年 4 月) 以降を展開する以外、特別な手順は必要ありません。  <br/> |[Skype for Business Online で Lync クライアント エクスペリエンスを使用する](user-experience.md#LyncwithSfBO) <br/> |
|Skype for Business Server 2015  <br/> |クライアント ビルド 4711.1002 (2015 年 4 月) 以降を展開する以外、特別な手順は必要ありません。  <br/> |[オンプレミスの Skype for Business Server で Lync クライアント エクスペリエンスを使用する](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 および Lync Server 2010  <br/> |[Skype クライアント エクスペリエンスを使用して、Lync Server 2013 または Lync Server 2010 の設置型の](user-experience.md#SkypewithLynconprem) <br/> |[Lync クライアント エクスペリエンスを使用して、Lync Server 2013 または Lync Server 2010 の設置型の](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Skype クライアント エクスペリエンスを使用して、Lync Server 2013 または Lync Server 2010 の設置型の
<a name="SkypewithLynconprem"> </a>

このセクションの手順は、オンプレミス環境で Skype クライアント エクスペリエンスを構成したい場合に実行します。これは、オンプレミスの既定のエクスペリエンスです。
  
 **手順 1:** まず、クライアントのポリシー設定をサポートしている Lync Server のバージョンを実行していることを確認してください。
  
- **Lync Server 2013** - を実行する必要があります 2014年 12 月の Lync Server 2013 またはそれ以降の更新プログラムの累積的な更新 (5.0.8308.857)。 詳細については、「[Lync Server 2013 用の更新プログラム](https://go.microsoft.com/fwlink/p/?LinkId=532772)」を参照してください。
    
- **Lync Server 2010** - を実行する必要があります 2015年 2 月の Lync Server 2010 またはそれ以降の更新プログラムの累積的な更新 (4.0.7577.710)。 については、 [Lync Server 2010 用の更新プログラム](https://go.microsoft.com/fwlink/p/?LinkId=532771)を参照してください。
    
  **手順 2:** 次に、ビジネス クライアント用の Skype と Skype クライアント エクスペリエンスを設定するのには、クライアント ポリシーを使用します。 クライアント ポリシーを使用して、クライアント エクスペリエンスを設定する場合、**3 つのオプション**があります。
  
  **オプション 1:** グローバル ポリシーを使用して、Skype クライアント エクスペリエンスを設定します。グローバル ポリシーは、展開に含まれるすべてのユーザーに適用されますが、ユーザー レベルおよびサイト レベルのポリシーの方がグローバル ポリシーよりも優先される点に注意してください。
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **オプション 2:** 現在環境で使用している既存のクライアント ポリシーを変更し、Skype クライアント エクスペリエンスを有効にする設定が含まれるようにします。この場合、既存のポリシーが割り当てられているユーザーのみに Skype クライアント エクスペリエンスを割り当てることができます。
  
```
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **オプション 3:** Skype クライアント エクスペリエンスの設定を含む新しいポリシーを作成して、ユーザーに割り当てます。最初に新しいクライアント ポリシーを作成してから、ポリシーの名前を **Identity** パラメーターの値として指定します。
  
```
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

次にポリシーの名前 (**Identity** パラメーターに使用した値) を **PolicyName** パラメーターの値として使用し、ユーザーにポリシーを割り当てます。
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **手順 3:** ビジネス クライアントでは、ビルド 4711.1002 (2015 年 4 月に) Skype を導入、クライアントのポリシーを構成した後またはそれ以降です。
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Lync クライアント エクスペリエンスを使用して、Lync Server 2013 または Lync Server 2010 の設置型の
<a name="LyncwithLynconprem"> </a>

これは、オンプレミスの Lync Server 展開のビジネス クライアント用の Skype を配置するときの既定の動作です。 Lync クライアントの操作性を使用するすべてのクライアント ポリシーを構成する必要はありませんが、クライアントの最初の実行動作を制御することができます。 既定では、ユーザーが初めてビジネス クライアント用の Skype を起動する、Skype クライアント エクスペリエンスが使用され、Lync クライアント エクスペリエンスを取得するクライアントを再起動することを要求するユーザーに通知が表示されます。 お客様の環境を構成するには、Lync クライアント エクスペリエンスには、最初にクライアントを起動するだけでなくユーザーのクライアント コンピューター上のシステム レジストリを変更することによってクライアントのチュートリアルをオフが表示されないようにします。 手順については、ビジネス クライアントは、次のトピックのいずれかを参照してください Skype を導入する前に実行する必要があります。
  
- **Lync Server 2013**では、 [Lync Server 2013 でビジネス用の Skype で発生するクライアントの構成](https://go.microsoft.com/fwlink/p/?LinkId=532732)を参照してください。
    
- **Lync Server 2010**は、 [Lync Server 2010 のビジネス用の Skype で発生するクライアントの構成](https://go.microsoft.com/fwlink/p/?LinkId=532733)を参照してください。
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>オンプレミスの Skype for Business Server で Lync クライアント エクスペリエンスを使用する
<a name="LyncwithSfBServer"> </a>

ビジネス サーバーの展開、設置 Skype の Lync クライアント エクスペリエンスを構成する場合は、このセクションの手順を従います。
  
このセクションの手順は、オンプレミス環境で Skype クライアント エクスペリエンスを構成したい場合に実行します。これは、オンプレミスの既定のエクスペリエンスです。
  
 **手順 1:** 最初に、サーバーのビジネスの Skype を展開します。
  
 **手順 2:** 次に、クライアントのビジネスの Skype での Lync クライアント エクスペリエンスを設定するのには、クライアント ポリシーを使用します。 クライアント ポリシーを使用して、クライアント エクスペリエンスを設定する場合、**3 つのオプション**があります。
  
 **オプション 1:** グローバル ポリシーを使用して、Lync クライアント エクスペリエンスを設定します。グローバル ポリシーは、展開に含まれるすべてのユーザーに適用されますが、ユーザー レベルおよびサイト レベルのポリシーの方がグローバル ポリシーよりも優先される点に注意してください。
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **オプション 2:** 現在環境で使用している既存のクライアント ポリシーを変更し、Lync クライアント エクスペリエンスを有効にする設定が含まれるようにします。この場合、既存のポリシーが割り当てられているユーザーのみに Lync クライアント エクスペリエンスを割り当てることができます。
  
```
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **オプション 3:** Lync クライアント エクスペリエンスの設定を含む新しいポリシーを作成して、ユーザーに割り当てます。最初に新しいクライアント ポリシーを作成してから、ポリシーの名前を **Identity** パラメーターの値として指定します。
  
```
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

次にポリシーの名前 (**Identity** パラメーターに使用した値) を **PolicyName** パラメーターの値として使用し、ユーザーにポリシーを割り当てます。
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **手順 3: 省略可能な**時の最初のユーザーがビジネス クライアント用の Skype を起動する既定では、-、Skype クライアント エクスペリエンスを使用し、Lync クライアント エクスペリエンスを取得するクライアントを再起動を要求することをユーザーに通知が表示されます。 お客様の環境を構成するには、Lync クライアント エクスペリエンスには、ユーザー、クライアントを起動すると、クライアント コンピューター上のシステム レジストリを変更することにより、クライアントのチュートリアルでは、オフには、最初が表示されないようにします。 ビジネス クライアント用の Skype を導入する前に実行する必要がある手順は、 [Skype のビジネスで発生するクライアントの構成](../../deploy/deploy-clients/configure-the-client-experience.md)を参照してください。
  
 **手順 4:** ビジネス クライアントでは、ビルド 4711.1002 (2015 年 4 月に) Skype を導入、クライアントのポリシーを構成した後またはそれ以降です。
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Skype for Business Online で Lync クライアント エクスペリエンスを使用する
<a name="LyncwithSfBO"> </a>

Lync クライアントの操作性とビジネス オンラインの Skype を使用するを構成する場合は、このセクションの手順を従います。
  
ビジネス オンラインの Skype を使用する場合も使用できます Lync クライアント エクスペリエンス、Skype でビジネスのクライアントの組織のクライアントのポリシーを構成するリモート PowerShell を使用しています。 クライアント ポリシーを使用して、クライアント エクスペリエンスを設定する場合、**3 つのオプション**があります。 ポリシーとパラメーターの名前とは異なるビジネスまたは Lync Server の Skype を使用している場合は、クライアント エクスペリエンスを構成するのにを使用する設定を設置します。
  
 **オプション 1:** グローバル ポリシーを使用して Lync クライアント エクスペリエンスを設定します。 ユーザーに適用されるクライアントとサイトのポリシーはグローバル ポリシーより優先されることを注意してください。
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **オプション 2:** 現在環境で使用している既存のクライアント ポリシーを変更し、Lync クライアント エクスペリエンスを有効にする設定が含まれるようにします。この場合、既存のポリシーが割り当てられているユーザーのみに Lync クライアント エクスペリエンスを割り当てることができます。
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **オプション 3:** Lync クライアント エクスペリエンスの設定を含むカスタム ポリシーのインスタンスを使用します。
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

ビジネス クライアントでは、ビルド 4711.1002 (2015 年 4 月に) Skype を導入、クライアントのポリシーを構成した後またはそれ以降です。
  
クライアントを構成する方法についての詳細な発生 Skype で、最初の実行経験とお客様の環境を構成するのにを使用することができます PowerShell スクリプトを制御する方法について手順を含むビジネス オンライン、[を参照するくださいとの間の切り替え、Skype ビジネスおよび Lync クライアントのユーザー インターフェイスの](https://aka.ms/SfBOUI)です。
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>サポート チームとエンド ユーザーの更新の準備に役立つリソース
<a name="support"> </a>

簡単にしてを組織の移行の準備、計画、教育、およびエンド ・ ユーザーに協力するため、その他多くのリソースがあります。
  
- [ビデオ: Skype for Business の概要](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Skype for Business クイック スタート ガイド (ダウンロード)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync はビジネス用の Skype では今すぐ、新機能を参照してください。](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype for Business: Step-by-step guide for new users (新しいユーザー向けのステップ バイ ステップ ガイド)](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Lync を使っているときに Skype for Business が表示されるのはなぜですか?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

