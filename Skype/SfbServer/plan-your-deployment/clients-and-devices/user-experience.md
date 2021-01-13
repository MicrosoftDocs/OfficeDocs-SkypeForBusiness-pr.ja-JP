---
title: ユーザーの Skype for Business 2015 クライアント エクスペリエンスを計画する
ms.author: v-cichur
author: cichur
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
description: '概要: Skype for Business Online、Skype for Business Server 2019、Skype for Business Server 2015、Lync Server 2013、または Lync Server 2010 を使用している場合に関係ない、新しい Skype for Business について、および環境とユーザーが更新プログラムを準備するために実行できる手順について説明します。'
ms.openlocfilehash: 1136bcf95a0c9ee045d9947bd7a2f7771dae16fd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813927"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>ユーザーの Skype for Business 2015 クライアント エクスペリエンスを計画する
 
**概要:** 新しい Skype for Business と、Skype for Business Online、Skype for Business Server 2019、Skype for Business Server 2015、Lync Server 2013、Lync Server 2010 を使用している場合に、環境とユーザーが更新プログラムを準備するために実行できる手順について説明します。
  
Lync 2013 Office 2015 年 4 月 14 日には、新しい Skype for Business ユーザー インターフェイスが含まれています。 この更新プログラムを使用すると、管理者はクライアントの外観を制御し、Lync 2013 クライアント エクスペリエンスを維持するか、改善された Skype for Business クライアント エクスペリエンスを使用するかどうかを選択できます。 Skype for Business クライアントは、Lync 2013 クライアントを効果的に置き換え、管理者が既存の Lync クライアント エクスペリエンスと新しい Skype for Business クライアント エクスペリエンスの中から選択する機能を追加しました。 この更新プログラムの詳細については [、Lync 2013 (Skype for Business) (KB2889923) 用の 2015](https://support.microsoft.com/kb/2889923/)年 4 月 14 日の更新プログラムを参照してください。
  
2015 年 5 月 12 日には、更新された Skype for Business クライアントを含む Office月次更新プログラムが追加されます。 4 月の更新プログラムを適用しなかった多くのお客様は、5 月 12 日の更新プログラムをOffice 2013。 このトピックの情報は、組織、環境、およびユーザーのクライアント更新の準備に役立ちます。 ユーザーとサポート チームが簡単に移行するには、このトピックの情報を使用して、ユーザーに必要なクライアント エクスペリエンスを決定し、組織にクライアント更新プログラムを展開する前に環境に変更を加えるのに役立ちます。
  
- [ユーザーに対してどのようなクライアント エクスペリエンスが必要か。](user-experience.md#clientexperience)
    
- [Skype for Business クライアント用の環境を準備する](user-experience.md#usinglync)
    
- [サポート チームとエンド ユーザーの更新準備に役立つリソース](user-experience.md#support)
    
> [!NOTE]
> Lync 2013 クライアント エクスペリエンスは、Skype for Business 2016 クライアント バージョンのオプションではありません。 Lync 2013 クライアントを使用するためのクライアント環境の構成を試みる前に、クライアントのバージョンを確認して、番号 16 で始まるのではないか確認してください。例: 16.x.x.x。 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>ユーザーに対してどのようなクライアント エクスペリエンスが必要か。
<a name="clientexperience"> </a>

新しい Skype for Business クライアントを使用すると、ユーザーが取得するクライアント エクスペリエンス (Lync または Skype for Business) を制御できます。 既定のクライアント エクスペリエンスは、Lync または Skype for Business オンプレミスを使用しているかオンラインを使用しているかによって異なります。 現在、Microsoft 365 Apps for enterprise、Microsoft 365 Business Standard、または Office 2013 で Skype for Business Online (Lync Online) を使用している場合、更新された Skype for Business クライアント エクスペリエンス (Skype の外観から着たもの) が既定のユーザー エクスペリエンスになります。 現在、オンプレミスの Lync Server を使用している場合、Lync クライアント エクスペリエンスが既定になります。
  
クライアント ポリシーを使用して、ユーザーが取得するクライアント エクスペリエンスを構成できます。 クライアント ポリシーは、ユーザーが Lync または Skype for Business にログインするときに適用される一連の構成設定です。
  
### <a name="skype-for-business-client-experience"></a>Skype for Business クライアント エクスペリエンス

Skype for Business は、Lync のすべての機能に加えて、簡素化されたコントロールと Skype の使い慣れたアイコンを備え、新機能を提供します。 Skype for Business の一部の新機能は、新しい Skype for Business クライアント エクスペリエンスでのみ利用できます。 Skype for Business の新機能の詳細については、「Skype for Business の検出」を [参照してください](https://go.microsoft.com/fwlink/p/?LinkId=528686)。
  
### <a name="lync-client-experience"></a>Lync クライアント エクスペリエンス

Lync クライアント エクスペリエンスは、ユーザーが既に理解している Lync 2013 クライアント エクスペリエンスと非常に似ていますが、ユーザーに知らせたい変更がいくつか存在します。 Lync クライアント エクスペリエンスと Lync 2013 クライアントの違いを確認するには [、Lync](https://go.microsoft.com/fwlink/p/?LinkId=544712) を使用している場合に Skype for Business が表示される理由と、このトピックの後半にあるその他のリンクを参照してください。
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Skype for Business クライアント用の環境を準備する
<a name="usinglync"> </a>

クライアントの更新に備え、環境を整えるには、いくつかの操作を行う必要があります。 クライアント エクスペリエンスを構成する変更を開始する前に、クライアント ポリシー設定をサポートするバージョンの Skype for Business Server または Lync Server を使用している必要があります。
  
クライアント エクスペリエンスを制御するポリシー設定をサポートするバージョンの Skype for Business Server または Lync Server を使用しているのを確認したら、環境内でポリシー設定を構成する必要があります。 従う必要がある具体的な手順は、使用している Skype for Business Server または Lync Server のバージョン、およびユーザーがオンプレミスかオンラインかによって異なっています。 
  
クライアント更新プログラムがユーザーに配信される前にこれらの変更を行い、ユーザーが初めて Skype for Business クライアントを起動してからクライアント エクスペリエンスを制御できます。 次の表は、ユーザーに必要なクライアント エクスペリエンスを提供するために環境を構成するために必要な手順を示しています。
  
|**展開**|**Skype for Business クライアント エクスペリエンス**|**Lync クライアント エクスペリエンス**|
|:-----|:-----|:-----|
|Skype for Business Online  <br/> |クライアント ビルド 4711.1002 (2015 年 4 月) 以降を展開する以外に、追加の手順はありません。  <br/> |[Skype for Business Online で Lync クライアント エクスペリエンスを使用する](user-experience.md#LyncwithSfBO) <br/> |
|Skype for Business Server 2015  <br/> |クライアント ビルド 4711.1002 (2015 年 4 月) 以降を展開する以外に、追加の手順はありません。  <br/> |[オンプレミスの Skype for Business Server で Lync クライアント エクスペリエンスを使用する](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 および Lync Server 2010  <br/> |[Lync Server 2013 または Lync Server 2010 オンプレミスで Skype クライアント エクスペリエンスを使用する](user-experience.md#SkypewithLynconprem) <br/> |[Lync Server 2013 または Lync Server 2010 オンプレミスで Lync クライアント エクスペリエンスを使用する](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Lync Server 2013 または Lync Server 2010 オンプレミスで Skype クライアント エクスペリエンスを使用する
<a name="SkypewithLynconprem"> </a>

オンプレミス展開で Skype クライアント エクスペリエンスを構成する場合は、このセクションの手順に従います。 オンプレミスの既定のエクスペリエンス
  
 **手順 1:** 最初に、クライアント ポリシー設定をサポートするバージョンの Lync Server が実行されている必要があります。
  
- **Lync Server 2013** - Lync Server 2013 以降の更新プログラムの 2014 年 12 月の累積的な更新プログラム (5.0.8308.857) を実行している必要があります。 詳細については [、「Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772)の更新プログラム」を参照してください。
    
- **Lync Server 2010** - Lync Server 2010 以降の更新プログラムの 2015 年 2 月の累積的な更新プログラム (4.0.7577.710) を実行している必要があります。 詳細については [、「Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)の更新プログラム」を参照してください。
    
  **手順 2:** 次に、クライアント ポリシーを使用して、Skype for Business クライアントで Skype クライアント エクスペリエンスを設定します。 クライアント ポリシー **を使用してクライアント** エクスペリエンスを設定するには、3 つのオプションがあります。
  
  **オプション 1:** グローバル ポリシーを使用して Skype クライアント エクスペリエンスを設定します。 グローバル ポリシーは展開内のすべてのユーザーに適用されますが、ユーザー レベルおよびサイト レベルのポリシーはグローバル ポリシーよりも優先されます。
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **オプション 2:** 環境で使用している既存のクライアント ポリシーを変更して、Skype クライアント エクスペリエンスを有効にする設定を含めます。 これにより、既存のポリシーが割り当てられているユーザーにのみ Skype クライアント エクスペリエンスを割り当てることができます。
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **オプション 3:** Skype クライアント エクスペリエンスの設定を含むユーザーに割り当てる新しいポリシーを作成します。 まず、新しいクライアント ポリシーを作成し、Identity パラメーターの値としてポリシーの名前を **指定** します。
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

次に、PolicyName パラメーターの値としてポリシーの名前 **(Identity** パラメーターに使用した値) を使用して、ポリシーをユーザーに **割り当** てる。
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **手順 3:** クライアント ポリシーを構成した後、Skype for Business クライアントビルド 4711.1002 (2015 年 4 月) 以降を展開します。
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Lync Server 2013 または Lync Server 2010 オンプレミスで Lync クライアント エクスペリエンスを使用する
<a name="LyncwithLynconprem"> </a>

これは、Skype for Business クライアントをオンプレミスの Lync Server 展開に展開する場合の既定のエクスペリエンスです。 Lync クライアント エクスペリエンスを使用するためにクライアント ポリシーを構成する必要はありません。ただし、クライアントの最初の実行動作を制御する必要がある場合があります。 既定では、ユーザーが初めて Skype for Business クライアントを起動すると、Skype クライアント エクスペリエンスが使用され、Lync クライアント エクスペリエンスを取得するためにクライアントの再起動を要求する通知がユーザーに表示されます。 ユーザーが初めてクライアントを起動すると Lync クライアント エクスペリエンスが表示される環境を構成できます。また、クライアント コンピューターのシステム レジストリを変更してクライアント チュートリアルをオフにすることもできます。 Skype for Business クライアントを展開する前に実行する必要がある手順については、次のいずれかのトピックを参照してください。
  
- **Lync Server 2013、Lync** [Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532732)での Skype for Business でのクライアント エクスペリエンスの構成を参照
    
- **Lync Server 2010「Lync** [Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532733)での Skype for Business でのクライアント エクスペリエンスの構成」を参照
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>オンプレミスの Skype for Business Server で Lync クライアント エクスペリエンスを使用する
<a name="LyncwithSfBServer"> </a>

オンプレミスの Skype for Business Server 展開で Lync クライアント エクスペリエンスを構成する場合は、このセクションの手順に従います。
  
オンプレミス展開で Skype クライアント エクスペリエンスを構成する場合は、このセクションの手順に従います。 オンプレミスの既定のエクスペリエンス
  
 **手順 1:** まず、Skype for Business Server を展開します。
  
 **手順 2:** 次に、クライアント ポリシーを使用して、Skype for Business クライアントで Lync クライアント エクスペリエンスを設定します。 クライアント ポリシー **を使用してクライアント** エクスペリエンスを設定するには、3 つのオプションがあります。
  
 **オプション 1:** グローバル ポリシーを使用して Lync クライアント エクスペリエンスを設定します。 グローバル ポリシーは展開内のすべてのユーザーに適用されますが、ユーザー レベルおよびサイト レベルのポリシーはグローバル ポリシーよりも優先されます。
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **オプション 2:** 環境で使用している既存のクライアント ポリシーを変更して、Lync クライアント エクスペリエンスを有効にする設定を含めます。 これにより、既存のポリシーが割り当てられているユーザーにのみ Lync クライアント エクスペリエンスを割り当てることができます。
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **オプション 3:** Lync クライアント エクスペリエンスの設定を含むユーザーに割り当てる新しいポリシーを作成します。 まず、新しいクライアント ポリシーを作成し、Identity パラメーターの値としてポリシーの名前を **指定** します。
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

次に、PolicyName パラメーターの値としてポリシーの名前 **(Identity** パラメーターに使用した値) を使用して、ポリシーをユーザーに **割り当** てる。
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **手順 3:** 省略可能 - 既定では、ユーザーが初めて Skype for Business クライアントを起動すると、Skype クライアント エクスペリエンスが使用され、Lync クライアント エクスペリエンスを取得するためにクライアントを再起動することを求める通知がユーザーに表示されます。 ユーザーが初めてクライアントを起動すると Lync クライアント エクスペリエンスが表示され、クライアント コンピューターのシステム レジストリを変更してクライアント チュートリアルをオフにできるよう環境を構成できます。 Skype for Business クライアントを展開する前に実行する必要がある手順については、「Skype for Business でクライアント エクスペリエンスを構成する」を [参照してください](../../deploy/deploy-clients/configure-the-client-experience.md)。
  
 **手順 4:** クライアント ポリシーを構成した後、Skype for Business クライアントビルド 4711.1002 (2015 年 4 月) 以降を展開します。
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Skype for Business Online で Lync クライアント エクスペリエンスを使用する
<a name="LyncwithSfBO"> </a>

Lync クライアント エクスペリエンスを構成し、Skype for Business Online を使用する場合は、このセクションの手順に従います。
  
Skype for Business Online を使用している場合でも、リモート PowerShell を使用してクライアント ポリシーを構成することで、組織内の Skype for Business クライアントで Lync クライアント エクスペリエンスを使用できます。 クライアント ポリシー **を使用してクライアント** エクスペリエンスを設定するには、3 つのオプションがあります。 ポリシー名とパラメーター名は、Skype for Business または Lync Server オンプレミスを使用している場合のクライアント エクスペリエンスの構成に使用する設定とは異なります。
  
 **オプション 1:** グローバル ポリシーを使用して Lync クライアント エクスペリエンスを設定します。 ユーザーに適用されるクライアント ポリシーとサイト ポリシーは、グローバル ポリシーよりも優先されます。
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **オプション 2:** 環境で使用している既存のクライアント ポリシーを変更して、Lync クライアント エクスペリエンスを有効にする設定を含めます。 これにより、既存のポリシーが割り当てられているユーザーにのみ Lync クライアント エクスペリエンスを割り当てることができます。
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **オプション 3:** Lync クライアント エクスペリエンスの設定を含むカスタム ポリシー インスタンスを使用します。
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

クライアント ポリシーを構成した後、Skype for Business クライアントビルド 4711.1002 (2015 年 4 月) 以降を展開します。
  
Skype for Business Online でクライアント エクスペリエンスを構成する方法の詳細については、「最初の実行エクスペリエンスを制御する方法に関する手順、環境の構成に使用できる PowerShell スクリプト」を含む [、「Skype for Business](https://aka.ms/SfBOUI)と Lync クライアントのユーザー インターフェイスを切り替える」を参照してください。
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>サポート チームとエンド ユーザーの更新準備に役立つリソース
<a name="support"> </a>

お客様と組織が移行に備えやすくするために、エンド ユーザーの計画、教育、関与に役立つその他のリソースが多数用意されています。
  
- [ビデオ: Skype for Business の概要](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Skype for Business クイック スタート ガイド (ダウンロード)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync が Skype for Business に変更 — 新機能を確認する](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype for Business: 新しいユーザー向けステップ バイ ステップ ガイド](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Lync を使用している場合に Skype for Business が表示される理由](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

