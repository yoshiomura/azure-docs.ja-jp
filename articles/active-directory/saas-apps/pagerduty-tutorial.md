---
title: チュートリアル:Azure Active Directory と PagerDuty の統合 | Microsoft Docs
description: Azure Active Directory と PagerDuty の間でシングル サインオンを構成する方法について説明します。
services: active-directory
documentationCenter: na
author: jeevansd
manager: daveba
ms.reviewer: joflore
ms.assetid: 0410456a-76f7-42a7-9bb5-f767de75a0e0
ms.service: active-directory
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 06/20/2018
ms.author: jeedes
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5c68fdadcf115f57ba524b1b4dc8a2c800cbfaf8
ms.sourcegitcommit: 301128ea7d883d432720c64238b0d28ebe9aed59
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2019
ms.locfileid: "56177922"
---
# <a name="tutorial-azure-active-directory-integration-with-pagerduty"></a>チュートリアル:Azure Active Directory と PagerDuty の統合

このチュートリアルでは、PagerDuty と Azure Active Directory (Azure AD) を統合する方法について説明します。

PagerDuty と Azure AD の統合には、次の利点があります。

- PagerDuty にアクセスする Azure AD ユーザーを制御できます。
- ユーザーが自分の Azure AD アカウントで自動的に PagerDuty にサインオン (シングル サインオン) できるようにすることが可能です。
- 1 つの中央サイト (Azure Portal) でアカウントを管理できます

SaaS アプリと Azure AD の統合の詳細については、「[Azure Active Directory のアプリケーション アクセスとシングル サインオンとは](../manage-apps/what-is-single-sign-on.md)」をご覧ください。

## <a name="prerequisites"></a>前提条件

PagerDuty と Azure AD の統合を構成するには、次のものが必要です。

- Azure AD サブスクリプション
- PagerDuty でのシングル サインオンが有効なサブスクリプション

> [!NOTE]
> このチュートリアルの手順をテストする場合、運用環境を使用しないことをお勧めします。

このチュートリアルの手順をテストするには、次の推奨事項に従ってください。

- 必要な場合を除き、運用環境は使用しないでください。
- Azure AD の評価環境がない場合は、[1 か月の評価版を入手できます](https://azure.microsoft.com/pricing/free-trial/)。

## <a name="scenario-description"></a>シナリオの説明
このチュートリアルでは、テスト環境で Azure AD のシングル サインオンをテストします。 このチュートリアルで説明するシナリオは、主に次の 2 つの要素で構成されています。

1. ギャラリーから PagerDuty を追加する
1. Azure AD シングル サインオンの構成とテスト

## <a name="adding-pagerduty-from-the-gallery"></a>ギャラリーから PagerDuty を追加する
Azure AD への PagerDuty の統合を構成するには、ギャラリーから管理対象 SaaS アプリの一覧に PagerDuty を追加する必要があります。

**ギャラリーから PagerDuty を追加するには、次の手順を実行します。**

1. **[Azure Portal](https://portal.azure.com)** の左側のナビゲーション ウィンドウで、**[Azure Active Directory]** アイコンをクリックします。

    ![Azure Active Directory のボタン][1]

1. **[エンタープライズ アプリケーション]** に移動します。 次に、**[すべてのアプリケーション]** に移動します。

    ![[エンタープライズ アプリケーション] ブレード][2]

1. 新しいアプリケーションを追加するには、ダイアログの上部にある **[新しいアプリケーション]** をクリックします。

    ![[新しいアプリケーション] ボタン][3]

1. 検索ボックスに「**PagerDuty**」と入力し、結果パネルで **[PagerDuty]** を選び、**[追加]** をクリックして、アプリケーションを追加します。

    ![Azure AD のテスト ユーザーの作成](./media/pagerduty-tutorial/tutorial_pagerduty_addfromgallery.png)

## <a name="configure-and-test-azure-ad-single-sign-on"></a>Azure AD シングル サインオンの構成とテスト

このセクションでは、"Britta Simon" というテスト ユーザーに基づいて、PagerDuty で Azure AD のシングル サインオンを構成し、テストします。

シングル サインオンを機能させるには、Azure AD ユーザーに対応する PagerDuty ユーザーが Azure AD で認識されている必要があります。 言い換えると、Azure AD ユーザーと PagerDuty の関連ユーザーの間で、リンク関係が確立されている必要があります。

PagerDuty で、Azure AD の **[ユーザー名]** の値を **[Username]** の値として割り当ててリンク関係を確立します。

PagerDuty で Azure AD のシングル サインオンを構成してテストするには、次の手順を完了する必要があります。

1. **[Azure AD シングル サインオンの構成](#configure-azure-ad-single-sign-on)** - ユーザーがこの機能を使用できるようにします。
1. **[Azure AD のテスト ユーザーの作成](#create-an-azure-ad-test-user)** - Britta Simon で Azure AD のシングル サインオンをテストします。
1. **[PagerDuty のテスト ユーザーの作成](#create-a-pagerduty-test-user)** - PagerDuty で Britta Simon に対応するユーザーを作成し、Azure AD の Britta Simon にリンクさせます。
1. **[Azure AD テスト ユーザーの割り当て](#assign-the-azure-ad-test-user)** - Britta Simon が Azure AD シングル サインオンを使用できるようにします。
1. **[シングル サインオンのテスト](#test-single-sign-on)** - 構成が機能するかどうかを確認します。

### <a name="configure-azure-ad-single-sign-on"></a>Azure AD シングル サインオンの構成

このセクションでは、Azure Portal で Azure AD のシングル サインオンを有効にして、PagerDuty アプリケーションでシングル サインオンを構成します。

**PagerDuty で Azure AD シングル サインオンを構成するには、次の手順に従います。**

1. Azure Portal の **PagerDuty** アプリケーション統合ページで、**[シングル サインオン]** をクリックします。

    ![シングル サインオン構成のリンク][4]

1. **[シングル サインオン]** ダイアログで、**[モード]** として **[SAML ベースのサインオン]** を選択し、シングル サインオンを有効にします。

    ![[シングル サインオン] ダイアログ ボックス](./media/pagerduty-tutorial/tutorial_pagerduty_samlbase.png)

1. **[PagerDuty のドメインと URL]** セクションで、次の手順に従います。

    ![[PagerDuty のドメインと URL] のシングル サインオン情報](./media/pagerduty-tutorial/tutorial_pagerduty_url.png)

    a. **[サインオン URL]** ボックスに、`https://<tenant-name>.pagerduty.com` のパターンを使用して URL を入力します。

    b. **[識別子]** ボックスに、`https://<tenant-name>.pagerduty.com` の形式で URL を入力します。

    > [!NOTE]
    > これらは実際の値ではありません。 実際のサインオン URL と識別子でこれらの値を更新してください。 これらの値を取得するには、[PagerDuty クライアント サポート チーム](https://www.pagerduty.com/support/)に問い合わせてください。

1. **[SAML 署名証明書]** セクションで、**[証明書 (Base64)]** をクリックし、コンピューターに証明書ファイルを保存します。

    ![証明書のダウンロードのリンク](./media/pagerduty-tutorial/tutorial_pagerduty_certificate.png)

1. **[保存]** ボタンをクリックします。

    ![[シングル サインオンの構成] の [保存] ボタン](./media/pagerduty-tutorial/tutorial_general_400.png)

1. **[PagerDuty 構成]** セクションで、**[PagerDuty の構成]** をクリックして、**[サインオンの構成]** ウィンドウを開きます。 **[クイック リファレンス]** セクションから**サインアウト URL と SAML シングル サインオン サービス URL** をコピーします。

    ![PagerDuty 構成](./media/pagerduty-tutorial/tutorial_pagerduty_configure.png)

1. 別の Web ブラウザーのウィンドウで、PagerDuty 企業サイトに管理者としてログインします。

1. 上部のメニューで **[アカウント設定]** をクリックします。

    ![Account Settings](./media/pagerduty-tutorial/ic778535.png "Account Settings")

1. **[Single Sign-on]** をクリックします。

    ![シングル サインオン](./media/pagerduty-tutorial/ic778536.png "シングル サインオン")

1. **[シングル サインオンの有効化 (SSO)]** ページで、次の手順に従います。

    ![シングル サインオンの有効化](./media/pagerduty-tutorial/ic778537.png "シングル サインオンの有効化")

    a. Azure Portal からダウンロードされた Base-64 でエンコードされた証明書をメモ帳で開き、その内容をクリップボードにコピーしてから、それを **[X.509 Certificate]** ボックスに貼り付けます
  
    b. **[Login URL]** ボックスに、Azure Portal からコピーした **SAML シングル サインオン サービス URL** を貼り付けます。
  
    c. **[Logout URL]** ボックスに、Azure Portal からコピーした**サインアウト URL** を貼り付けます。

    d.[Tableau Server return URL]: Tableau Server ユーザーがアクセスする URL。 **[Allow username/password login]**(ユーザー名/パスワードによるログインを許可) を選択します。

    e. **[Require EXACT authentication context comparison]**(認証コンテキストの正確な比較を要求する) チェック ボックスを選択します。

    f. **[変更を保存]** をクリックします。

### <a name="create-an-azure-ad-test-user"></a>Azure AD のテスト ユーザーの作成

このセクションの目的は、Azure Portal で Britta Simon というテスト ユーザーを作成することです。

![Azure AD のテスト ユーザーの作成][100]

**Azure AD でテスト ユーザーを作成するには、次の手順に従います。**

1. **Azure Portal** の左側のナビゲーション ウィンドウで、**[Azure Active Directory]** アイコンをクリックします。

    ![Azure Active Directory のボタン](./media/pagerduty-tutorial/create_aaduser_01.png) 

1. **[ユーザーとグループ]** に移動し、**[すべてのユーザー]** をクリックして、ユーザーの一覧を表示します。
    
    ![[ユーザーとグループ] と [すべてのユーザー] リンク](./media/pagerduty-tutorial/create_aaduser_02.png) 

1. ダイアログの上部にある **[追加]** をクリックして、**[ユーザー]** ダイアログを開きます。
 
    ![[追加] ボタン](./media/pagerduty-tutorial/create_aaduser_03.png) 

1. **[ユーザー]** ダイアログ ページで、次の手順を実行します。
 
    ![[ユーザー] ダイアログ ボックス](./media/pagerduty-tutorial/create_aaduser_04.png) 

    a. **[名前]** ボックスに「**BrittaSimon**」と入力します。

    b. **[ユーザー名]** ボックスに BrittaSimon の**電子メール アドレス**を入力します。

    c. **[パスワードを表示]** を選択し、**[パスワード]** の値をメモします。

    d.[Tableau Server return URL]: Tableau Server ユーザーがアクセスする URL。 **Create** をクリックしてください。
 
### <a name="create-a-pagerduty-test-user"></a>PagerDuty のテスト ユーザーの作成

Azure AD ユーザーが PagerDuty にログインできるようにするには、ユーザーを PagerDuty にプロビジョニングする必要があります。  
PagerDuty の場合、プロビジョニングは手動で行います。

>[!NOTE]
>PagerDuty から提供されている他の PagerDuty ユーザー アカウント作成ツールまたは API を使用して、Azure Active Directory ユーザー アカウントをプロビジョニングできます。

**ユーザー アカウントをプロビジョニングするには、次の手順に従います。**

1. **PagerDuty** テナントにログインします。

1. 上部のメニューで **[ユーザー]** をクリックします。

1. **[ユーザーの追加]** をクリックします。
   
    ![ユーザーの追加](./media/pagerduty-tutorial/ic778539.png "ユーザーの追加")

1.  **[Invite your team]** ダイアログ ボックスで、次の手順を実行します。
   
    ![チームの招待](./media/pagerduty-tutorial/ic778540.png "チームの招待")

    a. ユーザーの**氏名** (**Britta Simon** など) を入力します。 
   
    b. ユーザーの**電子メール** アドレス (**brittasimon@contoso.com** など) を入力します。
   
    c. **[Add]** をクリックし、**[Send Invites]** をクリックします。
   
    >[!NOTE]
    >PagerDuty アカウントを作成すると、追加したすべてのユーザーが招待を受信します。

### <a name="assign-the-azure-ad-test-user"></a>Azure AD テスト ユーザーの割り当て

このセクションでは、Britta Simon に PagerDuty へのアクセスを許可することで、このユーザーが Azure シングル サインオンを使用できるようにします。

![ユーザー ロールを割り当てる][200]

**PagerDuty に Britta Simon を割り当てるには、次の手順を実行します。**

1. Azure Portal でアプリケーション ビューを開き、ディレクトリ ビューに移動します。次に、**[エンタープライズ アプリケーション]** に移動し、**[すべてのアプリケーション]** をクリックします。

    ![ユーザーの割り当て][201] 

1. アプリケーションの一覧で **[PagerDuty]** を選択します。

    ![アプリケーションの一覧の PagerDuty のリンク](./media/pagerduty-tutorial/tutorial_pagerduty_app.png) 

1. 左側のメニューで **[ユーザーとグループ]** をクリックします。

    ![[ユーザーとグループ] リンク][202]

1. **[追加]** ボタンをクリックします。 次に、**[割り当ての追加]** ダイアログで **[ユーザーとグループ]** を選択します。

    ![[割り当ての追加] ウィンドウ][203]

1. **[ユーザーとグループ]** ダイアログで、ユーザーの一覧から **[Britta Simon]** を選択します。

1. **[ユーザーとグループ]** ダイアログで **[選択]** をクリックします。

1. **[割り当ての追加]** ダイアログで **[割り当て]** ボタンをクリックします。
    
### <a name="test-single-sign-on"></a>シングル サインオンのテスト

このセクションでは、アクセス パネルを使用して Azure AD のシングル サインオン構成をテストします。

アクセス パネルで [PagerDuty] タイルをクリックすると、PagerDuty アプリケーションに自動的にサインオンします。

アクセス パネルの詳細については、[アクセス パネルの概要](../user-help/active-directory-saas-access-panel-introduction.md)に関する記事を参照してください。

## <a name="additional-resources"></a>その他のリソース

* [SaaS アプリと Azure Active Directory を統合する方法に関するチュートリアルの一覧](tutorial-list.md)
* [Azure Active Directory のアプリケーション アクセスとシングル サインオンとは](../manage-apps/what-is-single-sign-on.md)

<!--Image references-->

[1]: ./media/pagerduty-tutorial/tutorial_general_01.png
[2]: ./media/pagerduty-tutorial/tutorial_general_02.png
[3]: ./media/pagerduty-tutorial/tutorial_general_03.png
[4]: ./media/pagerduty-tutorial/tutorial_general_04.png

[100]: ./media/pagerduty-tutorial/tutorial_general_100.png

[200]: ./media/pagerduty-tutorial/tutorial_general_200.png
[201]: ./media/pagerduty-tutorial/tutorial_general_201.png
[202]: ./media/pagerduty-tutorial/tutorial_general_202.png
[203]: ./media/pagerduty-tutorial/tutorial_general_203.png
