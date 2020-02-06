---
title: ユーザー向けの Skype for Business 2015 クライアントエクスペリエンスを計画する
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
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
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: '概要: Skype for Business Online を使用しているかどうかを確認し、skype for Business Online、skype for business Server 2019、Skype for Business Server 2015、Lync Server 2013 を使っているかどうかにかかわらず、環境とユーザーを準備するための手順について説明します。Lync Server 2010'
ms.openlocfilehash: afd0f9f8a764ef9430d9ac1a9887a872c02fedd7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803527"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>ユーザー向けの Skype for Business 2015 クライアントエクスペリエンスを計画する
 
**概要:** Skype for Business Online、Skype for business Online、skype for business server 2015 2019、Lync server 2013、Lync Server 2010 のいずれを使用している場合でも、新しい Skype for Business と、環境とユーザーを準備するための手順について説明します。
  
Lync 2013 用の2015年4月14日の Office 更新プログラムには、新しい Skype for Business のユーザーインターフェイスが含まれています。 この更新プログラムを使用すると、管理者はクライアントのルックアンドフィールを制御できるようになり、Lync 2013 クライアントエクスペリエンスを保持するか、強化された Skype for Business クライアントエクスペリエンスを使用するかを選ぶことができます。 Skype for Business クライアントが Lync 2013 クライアントを効果的に置き換えて、管理者が既存の Lync クライアントエクスペリエンスと新しい Skype for Business クライアントエクスペリエンスを選択できるようになりました。 この更新プログラムについては、 [2015 年4月14日の Lync 2013 用の更新プログラム (Skype For business) (KB2889923)](https://support.microsoft.com/en-us/kb/2889923/)を参照してください。
  
2015年5月12日に、更新された Skype for Business クライアントを含む別の月例の更新プログラムが Office にあります。 4月の更新プログラムが適用されていないお客様の多くは、Office 2013 の更新プログラム5月12日を選択します。 このトピックの情報は、クライアントの更新に対する組織、環境、ユーザーの準備に役立ちます。 ユーザーおよびサポート チームが容易に移行できるように、このトピックの情報を使用して、ユーザーに対してどちらのクライアント エクスペリエンスを使用するかを決定し、組織でクライアント更新プログラムを展開する前に環境に変更を加えてください。
  
- [What client experience do you want for your users?](user-experience.md#clientexperience)
    
- [Skype for Business クライアント用に環境を準備する](user-experience.md#usinglync)
    
- [Resources to help you prepare your support teams and your end users for the update](user-experience.md#support)
    
> [!NOTE]
> Lync 2013 クライアントエクスペリエンスは、Skype for Business 2016 クライアントバージョンでは使用できません。 Lync 2013 クライアントを使用するようにクライアント環境を構成する前に、クライアント バージョンを調べて、バージョンの先頭が 16 ではない (16.x.x.x などではない) ことを確認してください。 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>ユーザーに対して必要なクライアント エクスペリエンスは何ですか?
<a name="clientexperience"> </a>

新しい Skype for Business クライアントを使うと、ユーザーが Lync または Skype for Business のいずれのクライアントエクスペリエンスを利用できるかを制御できます。 既定のクライアントエクスペリエンスは、Lync と Skype for Business のオンプレミスまたはオンラインのどちらを使用しているかによって異なります。 Skype for Business Online (Lync Online) を使用しているときに、Office 365 ProPlus、Office 365 Business Premium、または Office 2013 を使用している場合、更新された Skype for Business クライアントエクスペリエンスが、Skype のルックアンドフィールによって、既定のユーザーエクスペリエンスとして表示されます。 現在オンプレミスの Lync Server を使用している場合は、Lync クライアントエクスペリエンスが既定になります。
  
クライアント ポリシーを使用することにより、ユーザーにどちらのクライアント エクスペリエンスを提供するか設定できます。 クライアントポリシーは、ユーザーが Lync または Skype for Business にログインしたときにユーザーに適用される構成設定のセットです。
  
### <a name="skype-for-business-client-experience"></a>Skype for Business クライアント エクスペリエンス

Skype for Business には、Lync のすべての機能に加えて、簡単なコントロールと Skype の使い慣れたアイコンが付いた新機能が用意されています。 Skype for Business の新機能の一部は、新しい Skype for Business クライアントエクスペリエンスでのみ利用できます。 Skype for Business の新機能の詳細については、「 [skype](https://go.microsoft.com/fwlink/p/?LinkId=528686)for business について」を参照してください。
  
### <a name="lync-client-experience"></a>Lync クライアント エクスペリエンス

Lync クライアント エクスペリエンスは、多くのユーザーが既に使いなれている Lync 2013 のクライアント エクスペリエンスによく似ていますが、いくつかの変更点についてユーザーに知らせておく必要があります。 Lync クライアントエクスペリエンスと Lync 2013 クライアントの違いについては、「 [lync を使っているときに Skype For business が表示](https://go.microsoft.com/fwlink/p/?LinkId=544712)される理由」およびこのトピックで後述する追加のリンクを参照してください。
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Skype for Business クライアント用に環境を準備する
<a name="usinglync"> </a>

クライアントの更新に向けて環境を準備するのに必要な作業はそれほど多くありません。 クライアントエクスペリエンスを構成するための変更を開始する前に、まずクライアントのポリシー設定をサポートするバージョンの Skype for Business Server または Lync Server を使用していることを確認する必要があります。
  
クライアントエクスペリエンスを制御するためのポリシー設定をサポートしているバージョンの Skype for Business Server または Lync Server を使用していることを確認したら、環境でポリシー設定を構成する必要があります。 実行する必要がある具体的な手順は、使用している Skype for Business Server または Lync Server のバージョン、およびユーザーがオンプレミスかオンラインかによって異なります。 
  
これらの変更は、クライアント更新プログラムがユーザーに配信される前に行う必要があります。これにより、Skype for Business クライアントを初めて起動したときに、クライアントのエクスペリエンスを制御することができます。 次の表では、ユーザーのために目的のクライアントエクスペリエンスの環境を構成するために必要な手順について説明します。
  
|**Deployment**|**Skype for Business クライアント エクスペリエンス**|**Lync クライアント エクスペリエンス**|
|:-----|:-----|:-----|
|Skype for Business Online  <br/> |クライアント ビルド 4711.1002 (2015 年 4 月) 以降を展開する以外、特別な手順は必要ありません。  <br/> |[Skype for Business Online で Lync クライアント エクスペリエンスを使用する](user-experience.md#LyncwithSfBO) <br/> |
|Skype for Business Server 2015  <br/> |クライアント ビルド 4711.1002 (2015 年 4 月) 以降を展開する以外、特別な手順は必要ありません。  <br/> |[オンプレミスの Skype for Business Server で Lync クライアント エクスペリエンスを使用する](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 および Lync Server 2010  <br/> |[Lync Server 2013 または Lync Server 2010 オンプレミスで Skype クライアントエクスペリエンスを使用する](user-experience.md#SkypewithLynconprem) <br/> |[Lync Server 2013 または Lync Server 2010 オンプレミスで Lync クライアントエクスペリエンスを使用する](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Lync Server 2013 または Lync Server 2010 オンプレミスで Skype クライアントエクスペリエンスを使用する
<a name="SkypewithLynconprem"> </a>

このセクションの手順は、オンプレミス環境で Skype クライアント エクスペリエンスを構成したい場合に実行します。これは、オンプレミスの既定のエクスペリエンスです。
  
 **手順 1:** まず、クライアントのポリシー設定をサポートしているバージョンの Lync Server を実行していることを確認します。
  
- **Lync server 2013** -lync server 2013 またはそれ以降の更新プログラムについては、2014年12月の累積更新プログラム (5.0.8308.857) を実行している必要があります。 詳細については、「 [Lync Server 2013 の更新プログラム](https://go.microsoft.com/fwlink/p/?LinkId=532772)」を参照してください。
    
- **Lync server 2010** -lync server 2010 またはそれ以降の更新プログラムについては、2015年2月の累積更新プログラム (4.0.7577.710) を実行している必要があります。 詳細については、「 [Lync Server 2010 の更新プログラム](https://go.microsoft.com/fwlink/p/?LinkId=532771)」を参照してください。
    
  **手順 2:** 次に、クライアントポリシーを使用して、skype for Business クライアントを使って Skype クライアントの操作環境を設定します。 クライアント ポリシーを使用して、クライアント エクスペリエンスを設定する場合、**3 つのオプション**があります。
  
  **オプション 1:** グローバル ポリシーを使用して、Skype クライアント エクスペリエンスを設定します。グローバル ポリシーは、展開に含まれるすべてのユーザーに適用されますが、ユーザー レベルおよびサイト レベルのポリシーの方がグローバル ポリシーよりも優先される点に注意してください。
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **オプション 2:** 現在環境で使用している既存のクライアント ポリシーを変更し、Skype クライアント エクスペリエンスを有効にする設定が含まれるようにします。この場合、既存のポリシーが割り当てられているユーザーのみに Skype クライアント エクスペリエンスを割り当てることができます。
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **オプション 3:** Skype クライアント エクスペリエンスの設定を含む新しいポリシーを作成して、ユーザーに割り当てます。最初に新しいクライアント ポリシーを作成してから、ポリシーの名前を **Identity** パラメーターの値として指定します。
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

次にポリシーの名前 (**Identity** パラメーターに使用した値) を **PolicyName** パラメーターの値として使用し、ユーザーにポリシーを割り当てます。
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **手順 3:** クライアントポリシーを構成したら、Skype for Business クライアント、ビルド 4711.1002 (4 月、2015) 以降を展開します。
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Lync Server 2013 または Lync Server 2010 オンプレミスで Lync クライアントエクスペリエンスを使用する
<a name="LyncwithLynconprem"> </a>

これは、Skype for Business クライアントがオンプレミスの Lync Server 展開に展開されるときの既定のエクスペリエンスです。 Lync クライアントエクスペリエンスを使用するようにクライアントポリシーを構成する必要はありませんが、クライアントの最初の実行動作を制御することができます。 既定では、ユーザーが Skype for Business クライアントを初めて起動すると、Skype クライアントエクスペリエンスが使用され、クライアントを再起動して Lync クライアントエクスペリエンスを取得するように要求したユーザーに通知が表示されます。 ユーザーが初めてクライアントを起動したときに Lync クライアントエクスペリエンスが表示されるように環境を構成し、クライアントコンピューターのシステムレジストリを変更して、クライアントのチュートリアルをオフにすることができます。 Skype for Business クライアントを展開する前に実行する必要がある手順については、次のいずれかのトピックを参照してください。
  
- **Lync server 2013**については、「 [lync Server 2013 で Skype for business を使用してクライアントエクスペリエンスを構成する](https://go.microsoft.com/fwlink/p/?LinkId=532732)」を参照してください。
    
- **Lync server 2010** 「 [lync Server 2010 の Skype for business でクライアントエクスペリエンスを構成する](https://go.microsoft.com/fwlink/p/?LinkId=532733)」を参照してください。
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>オンプレミスの Skype for Business Server で Lync クライアント エクスペリエンスを使用する
<a name="LyncwithSfBServer"> </a>

オンプレミスの Skype for Business Server 展開で Lync クライアントエクスペリエンスを構成する場合は、このセクションの手順に従います。
  
このセクションの手順は、オンプレミス環境で Skype クライアント エクスペリエンスを構成したい場合に実行します。これは、オンプレミスの既定のエクスペリエンスです。
  
 **手順 1:** まず、Skype for Business Server を展開します。
  
 **手順 2:** 次に、クライアントポリシーを使用して、Lync クライアントのエクスペリエンスを Skype for Business クライアントに設定します。 クライアント ポリシーを使用して、クライアント エクスペリエンスを設定する場合、**3 つのオプション**があります。
  
 **オプション 1:** グローバル ポリシーを使用して、Lync クライアント エクスペリエンスを設定します。グローバル ポリシーは、展開に含まれるすべてのユーザーに適用されますが、ユーザー レベルおよびサイト レベルのポリシーの方がグローバル ポリシーよりも優先される点に注意してください。
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **オプション 2:** 現在環境で使用している既存のクライアント ポリシーを変更し、Lync クライアント エクスペリエンスを有効にする設定が含まれるようにします。この場合、既存のポリシーが割り当てられているユーザーのみに Lync クライアント エクスペリエンスを割り当てることができます。
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **オプション 3:** Lync クライアント エクスペリエンスの設定を含む新しいポリシーを作成して、ユーザーに割り当てます。最初に新しいクライアント ポリシーを作成してから、ポリシーの名前を **Identity** パラメーターの値として指定します。
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

次にポリシーの名前 (**Identity** パラメーターに使用した値) を **PolicyName** パラメーターの値として使用し、ユーザーにポリシーを割り当てます。
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **手順 3: 省略可能。** 既定では、ユーザーが Skype for business クライアントを初めて起動したときに、skype クライアントエクスペリエンスが使用され、ユーザーにクライアントを再起動して Lync クライアントエクスペリエンスを取得するように求める通知が表示されます。 ユーザーがクライアントを初めて起動したときに Lync クライアントエクスペリエンスが表示されるように環境を構成することもできます。また、クライアントコンピューターのシステムレジストリを変更して、クライアントのチュートリアルをオフにします。 Skype for Business クライアントを展開する前に実行する必要がある手順については、「 [skype For business でクライアントエクスペリエンスを構成](../../deploy/deploy-clients/configure-the-client-experience.md)する」を参照してください。
  
 **手順 4:** クライアントポリシーを構成したら、Skype for Business クライアント、ビルド 4711.1002 (4 月、2015) 以降を展開します。
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Skype for Business Online で Lync クライアント エクスペリエンスを使用する
<a name="LyncwithSfBO"> </a>

Lync クライアントエクスペリエンスを構成し、Skype for Business Online を使用する場合は、このセクションの手順に従います。
  
Skype for Business Online を使用している場合でも、リモート PowerShell を使用してクライアントポリシーを構成することにより、組織内の Skype for Business クライアントで Lync クライアントエクスペリエンスを使用できます。 クライアント ポリシーを使用して、クライアント エクスペリエンスを設定する場合、**3 つのオプション**があります。 オンプレミスの Skype for Business または Lync Server を使用している場合、ポリシー名とパラメーター名は、クライアントエクスペリエンスを構成するために使用する設定とは異なります。
  
 **オプション 1:** グローバルポリシーを使用して、Lync クライアントの操作環境を設定します。 ユーザーに適用されたクライアントとサイトのポリシーは、グローバルポリシーよりも優先されることに注意してください。
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **オプション 2:** 現在環境で使用している既存のクライアント ポリシーを変更し、Lync クライアント エクスペリエンスを有効にする設定が含まれるようにします。この場合、既存のポリシーが割り当てられているユーザーのみに Lync クライアント エクスペリエンスを割り当てることができます。
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **オプション 3:** Lync クライアントエクスペリエンスの設定を含むカスタムポリシーインスタンスを使用します。
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

クライアントポリシーを構成したら、Skype for Business クライアント、ビルド 4711.1002 (4 月、2015) 以降を展開します。
  
Skype for Business Online でクライアントエクスペリエンスを構成する方法の詳細については、「Skype for business[と Lync クライアントのユーザーインターフェイスを切り替える](https://aka.ms/SfBOUI)」を参照して、最初の実行環境を制御する方法について説明します。
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>サポート チームとエンド ユーザーの更新の準備に役立つリソース
<a name="support"> </a>

自分と組織がより簡単に切り替えられるようにするために、エンドユーザーの計画、教育、および参加に役立つ多くのリソースが用意されています。
  
- [ビデオ: Skype for Business のご紹介](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Skype for Business クイックスタートガイド (ダウンロード)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync が Skype for Business に変わりました—新機能の紹介](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype for Business: 新規ユーザー向けのステップバイステップガイド](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Lync を使用しているときに Skype for Business が表示されるのはなぜですか?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

