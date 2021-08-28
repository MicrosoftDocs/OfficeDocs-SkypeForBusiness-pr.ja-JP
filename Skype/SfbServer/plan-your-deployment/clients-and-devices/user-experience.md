---
title: ユーザー向Skype for Business 2015 クライアント エクスペリエンスを計画する
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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: '概要: Skype for Business Online、Skype for Business Server 2019、Skype for Business Server 2015、Lync Server 2013、Lync Server 2010 を使用している場合に関係ない、新しい Skype for Business と更新プログラムの準備に使用できる手順について説明します。'
ms.openlocfilehash: b9ead36cb38c41376c80a85f1356e24e78b51eb7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586869"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>ユーザー向Skype for Business 2015 クライアント エクスペリエンスを計画する
 
**概要:** Skype for Business Online、Skype for Business Server 2019、Skype for Business Server 2015、Lync Server 2013、Lync Server 2010 を使用している場合に関係ない、環境と更新プログラムのユーザーを準備するために実行できる新しい Skype for Business と手順について説明します。
  
2015 年 4 月 14 日Office Lync 2013 の更新プログラムには、新しいユーザー インターフェイスSkype for Business含まれています。 この更新プログラムを使用すると、管理者はクライアントの外観を制御し、Lync 2013 クライアント エクスペリエンスを維持するか、改善されたクライアント エクスペリエンスを使用Skype for Business選択できます。 クライアントSkype for Business Lync 2013 クライアントを効果的に置き換え、管理者が既存の Lync クライアント エクスペリエンスと新しい Skype for Business クライアント エクスペリエンスの間で選択する機能を追加しました。 この更新プログラムの詳細については[、「April 14, 2015 update for Lync 2013 (Skype for Business) (KB2889923)」を参照](https://support.microsoft.com/kb/2889923/)してください。
  
2015 年 5 月 12 日には、更新されたクライアントを含む Office月次更新プログラムSkype for Businessされます。 4 月の更新プログラムを適用しなかった多くのお客様は、2013 年 5 月 12 日の更新Office予定です。 このトピックの情報は、組織、環境、およびユーザーをクライアント更新用に準備するのに役立ちます。 ユーザーとサポート チームの移行を簡単に行う場合は、このトピックの情報を使用して、ユーザーに必要なクライアント エクスペリエンスを決定し、組織にクライアント更新プログラムを展開する前に環境に変更を加えます。
  
- [ユーザーに必要なクライアント エクスペリエンス](user-experience.md#clientexperience)
    
- [クライアントの環境をSkype for Businessする](user-experience.md#usinglync)
    
- [サポート チームとエンド ユーザーの更新の準備に役立つリソース](user-experience.md#support)
    
> [!NOTE]
> Lync 2013 クライアント エクスペリエンスは、2016 クライアント バージョンSkype for Businessオプションではありません。 Lync 2013 クライアントを使用するクライアント環境を構成する前に、クライアントのバージョンを確認して、番号 16 で始まるのを確認してください。たとえば、16.x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>ユーザーに必要なクライアント エクスペリエンス
<a name="clientexperience"> </a>

新しいクライアント Skype for Businessを使用して、Lync またはユーザーが取得するクライアント エクスペリエンスをSkype for Business。 既定のクライアント エクスペリエンスは、Lync を使用しているか、オンプレミスまたはオンラインSkype for Business使用しているかによって異なります。 Microsoft 365 Apps for enterprise、Microsoft 365 Business Standard、または Office 2013 で今日 Skype for Business Online (Lync Online) を使用している場合は、Skype の外観に影響を受けた更新された Skype for Business クライアント エクスペリエンスが既定のユーザー エクスペリエンスになります。 現在 Lync Server オンプレミスを使用している場合は、Lync クライアント エクスペリエンスが既定になります。
  
クライアント ポリシーを使用して、ユーザーが取得するクライアント エクスペリエンスを構成できます。 クライアント ポリシーは、Lync またはユーザーにログインするときにユーザーに適用される構成設定のセットSkype for Business。
  
### <a name="skype-for-business-client-experience"></a>Skype for Businessエクスペリエンス

Lync のすべての機能に加えて、Skype for Business は、簡単なコントロールと使い慣れたアイコンを備Skype。 一部の新機能はSkype for Businessクライアント エクスペリエンスでのみSkype for Business利用できます。 新しい機能の詳細については、「Skype for Business」[を参照Skype for Business。](https://go.microsoft.com/fwlink/p/?LinkId=528686)
  
### <a name="lync-client-experience"></a>Lync クライアント エクスペリエンス

Lync クライアント エクスペリエンスは、ユーザーが既に理解している Lync 2013 クライアント エクスペリエンスとよく似ていますが、ユーザーに知らせたい変更がいくつかある場合があります。 Lync クライアント エクスペリエンスと Lync 2013 クライアントの違いを確認するには[、「Lync](https://go.microsoft.com/fwlink/p/?LinkId=544712)を使用している場合に Skype for Business が表示される理由」と、このトピックの後半の追加リンクを参照してください。
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>クライアントの環境をSkype for Businessする
<a name="usinglync"> </a>

クライアント更新の準備を整えるには、いくつかの操作が必要です。 クライアント エクスペリエンスを構成する変更を開始する前に、まず、クライアント ポリシー設定をサポートするバージョンの Skype for Business Server または Lync Server を使用している必要があります。
  
ポリシー設定をサポートする Skype for Business Server または Lync Server のバージョンを使用してクライアント エクスペリエンスを制御しているのを確認したら、環境でポリシー設定を構成する必要があります。 従う必要がある具体的な手順は、使用している Skype for Business Server Lync Server のバージョン、およびユーザーがオンプレミスかオンラインかによって異なっています。 
  
クライアント更新プログラムがユーザーに配信される前に、これらの変更を行って、クライアントがクライアントを初めて起動した時からクライアント エクスペリエンスを制御Skype for Businessがあります。 次の表は、ユーザーに必要なクライアント エクスペリエンスの環境を構成するために必要な手順を示しています。
  
|**展開**|**Skype for Businessエクスペリエンス**|**Lync クライアント エクスペリエンス**|
|:-----|:-----|:-----|
|Skype for Business Online  <br/> |クライアント ビルド 4711.1002 (2015 年 4 月) 以降を展開する以外に、追加の手順はありません。  <br/> |[Lync クライアント エクスペリエンスをオンラインでSkype for Businessする](user-experience.md#LyncwithSfBO) <br/> |
|Skype for Business Server 2015  <br/> |クライアント ビルド 4711.1002 (2015 年 4 月) 以降を展開する以外に、追加の手順はありません。  <br/> |[Lync クライアント エクスペリエンスをオンプレミスSkype for Business Server使用する](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 および Lync Server 2010  <br/> |[Lync Server 2013 Skype Lync Server 2010 オンプレミスでのクライアント エクスペリエンスの使用](user-experience.md#SkypewithLynconprem) <br/> |[Lync Server 2013 または Lync Server 2010 オンプレミスでの Lync クライアント エクスペリエンスの使用](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Lync Server 2013 Skype Lync Server 2010 オンプレミスでのクライアント エクスペリエンスの使用
<a name="SkypewithLynconprem"> </a>

オンプレミス展開でクライアント エクスペリエンスを構成する場合は、このSkype手順に従います。 オンプレミスの既定のエクスペリエンス
  
 **手順 1:** 最初に、クライアント ポリシー設定をサポートするバージョンの Lync Server を実行してください。
  
- **Lync Server 2013** - Lync Server 2013 以降の更新プログラムの 2014 年 12 月の累積的な更新プログラム (5.0.8308.857) を実行している必要があります。 詳細については [、「Updates for Lync Server 2013」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=532772)。
    
- **Lync Server 2010** - Lync Server 2010 以降の更新プログラムの 2015 年 2 月の累積的な更新プログラム (4.0.7577.710) を実行している必要があります。 詳細については [、「Updates for Lync Server 2010」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=532771)。
    
  **手順 2:** 次に、クライアント ポリシーを使用して、クライアント Skypeエクスペリエンスを設定Skype for Businessします。 クライアント ポリシー **を使用してクライアント** エクスペリエンスを設定するには、3 つのオプションがあります。
  
  **オプション 1:** グローバル ポリシーをSkypeして、クライアント エクスペリエンスを設定します。 グローバル ポリシーは展開内のすべてのユーザーに適用されますが、ユーザー およびサイト レベルのポリシーはグローバル ポリシーよりも優先されます。
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **オプション 2:** 環境で使用している既存のクライアント ポリシーを変更して、設定を含め、クライアント エクスペリエンスをSkypeします。 これにより、既存のポリシー Skypeユーザーにのみクライアント エクスペリエンスを割り当てることができます。
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **オプション 3:** クライアント エクスペリエンスの設定を含むユーザーに割り当てる新しいSkype作成します。 最初に、新しいクライアント ポリシーを作成し、Identity パラメーターの値としてポリシーの名前を **指定** します。
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

次に、ポリシーの名前 **(Identity** パラメーターに使用した値) を PolicyName パラメーターの値として使用して、ポリシーをユーザーに **割り当** てる。
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **手順 3:** クライアント ポリシーを構成した後、Skype for Business クライアントを展開し、4711.1002 (2015 年 4 月) 以降をビルドします。
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Lync Server 2013 または Lync Server 2010 オンプレミスでの Lync クライアント エクスペリエンスの使用
<a name="LyncwithLynconprem"> </a>

これは、オンプレミスの Lync Server 展開Skype for Businessクライアントが展開される既定のエクスペリエンスです。 Lync クライアント エクスペリエンスを使用するクライアント ポリシーを構成する必要はありません。ただし、クライアントの最初の実行動作を制御する必要があります。 既定では、ユーザーが初めて Skype for Business クライアントを起動すると、Skype クライアント エクスペリエンスが使用され、Lync クライアント エクスペリエンスを取得するためにクライアントを再起動する要求をユーザーに通知が表示されます。 ユーザーが初めてクライアントを起動すると Lync クライアント エクスペリエンスが表示されるだけでなく、クライアント コンピューター上のシステム レジストリを変更してクライアント チュートリアルをオフにできるよう環境を構成できます。 クライアントを展開する前に実行する必要Skype for Business手順については、次のいずれかのトピックを参照してください。
  
- **「Lync Server 2013** でのクライアント エクスペリエンスの構成」を参照 [Skype for Business Lync Server 2013](/previous-versions/office/lync-server-2013/configure-the-skype-for-business-client-in-lync-server-2013)
    
- **「Lync Server 2010** でのクライアント エクスペリエンスの構成」を参照 [Skype for Business Lync Server 2010](/previous-versions/office/skype-server-2010/dn955209(v=ocs.14))
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Lync クライアント エクスペリエンスをオンプレミスSkype for Business Server使用する
<a name="LyncwithSfBServer"> </a>

オンプレミスの展開で Lync クライアント エクスペリエンスを構成する場合は、このセクションの手順にSkype for Business Serverします。
  
オンプレミス展開でクライアント エクスペリエンスを構成する場合は、このSkype手順に従います。 オンプレミスの既定のエクスペリエンス
  
 **手順 1:** 最初に、次のSkype for Business Server。
  
 **手順 2:** 次に、クライアント ポリシーを使用して、Lync クライアント エクスペリエンスをクライアントクライアントSkype for Businessします。 クライアント ポリシー **を使用してクライアント** エクスペリエンスを設定するには、3 つのオプションがあります。
  
 **オプション 1:** グローバル ポリシーを使用して Lync クライアント エクスペリエンスを設定します。 グローバル ポリシーは展開内のすべてのユーザーに適用されますが、ユーザー およびサイト レベルのポリシーはグローバル ポリシーよりも優先されます。
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **オプション 2:** 環境で使用している既存のクライアント ポリシーを変更して、Lync クライアント エクスペリエンスを有効にする設定を含めます。 これにより、既存のポリシーが割り当てられているユーザーにのみ Lync クライアント エクスペリエンスを割り当てることができます。
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **オプション 3:** Lync クライアント エクスペリエンスの設定を含むユーザーに割り当てる新しいポリシーを作成します。 最初に、新しいクライアント ポリシーを作成し、Identity パラメーターの値としてポリシーの名前を **指定** します。
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

次に、ポリシーの名前 **(Identity** パラメーターに使用した値) を PolicyName パラメーターの値として使用して、ポリシーをユーザーに **割り当** てる。
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **手順 3:** オプション - 既定では、ユーザーが初めて Skype for Business クライアントを起動すると、Skype クライアント エクスペリエンスが使用され、Lync クライアント エクスペリエンスを取得するためにクライアントを再起動することを求める通知がユーザーに表示されます。 クライアント コンピューター上のシステム レジストリを変更することで、ユーザーが初めてクライアントを起動し、クライアント チュートリアルをオフにした場合に Lync クライアント エクスペリエンスが表示される環境を構成できます。 クライアントを展開する前に実行する必要がある手順については、「Skype for Businessを使用してクライアント エクスペリエンスを構成する」[をSkype for Business。](../../deploy/deploy-clients/configure-the-client-experience.md)
  
 **手順 4:** クライアント ポリシーを構成した後、Skype for Business クライアントを展開し、4711.1002 (2015 年 4 月) 以降をビルドします。
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Lync クライアント エクスペリエンスをオンラインでSkype for Businessする
<a name="LyncwithSfBO"> </a>

Lync クライアント エクスペリエンスを構成し、Lync クライアント エクスペリエンスをオンラインで使用する場合は、このセクションのSkype for Businessします。
  
Skype for Business Online を使用している場合でも、リモート PowerShell を使用してクライアント ポリシーを構成することで、組織内の Skype for Business クライアントで Lync クライアント エクスペリエンスを使用できます。 クライアント ポリシー **を使用してクライアント** エクスペリエンスを設定するには、3 つのオプションがあります。 ポリシー名とパラメーター名は、オンプレミスまたは Lync Server を使用するときにクライアント エクスペリエンスを構成するために使用するSkype for Business異なっています。
  
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

クライアント ポリシーを構成した後、Skype for Business クライアントを展開し、4711.1002 (2015 年 4 月) 以降をビルドします。
  
Skype for Business Online でクライアント エクスペリエンスを構成する方法の詳細については、「環境を構成するために使用できる最初の実行エクスペリエンスと PowerShell スクリプトを制御する方法」の手順を含む[、「Skype for Business](../../../SfbOnline/set-up-skype-for-business-online/switching-the-skype-for-business-and-the-lync-client-user-interfaces.md)と Lync クライアント ユーザー インターフェイスの切り替え」を参照してください。
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>サポート チームとエンド ユーザーの更新の準備に役立つリソース
<a name="support"> </a>

ユーザーと組織が移行の準備を容易にするために、エンド ユーザーの計画、教育、エンゲージに役立つ多くの追加リソースが用意されています。
  
- [ビデオ: Skype for Business の概要](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Skype for Businessクイック スタート ガイド (ダウンロード)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync は現在Skype for Business新しい情報を参照してください。](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype for Business: 新しいユーザー向けステップ バイ ステップ ガイド](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Lync を使用しているSkype for Businessが表示される理由](https://go.microsoft.com/fwlink/p/?LinkID=544712)
