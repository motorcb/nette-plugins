Usage:

1) Config (DI)

	factories:
		FbToolsScript:
			class: \FbTools\Script

		FbToolsLikeButton:
			class: \FbTools\LikeButton
			setup:
				- setContext(...)
				- setUrl('http://www.mojestranka.cz')
				- setWidth(150)
				.. or ..
				- setAll([
					url: 'http://www.mojestranka.cz',
					font: 'netusim',
					send: false,
					])

2) Presenter

protected function createComponentLikeButton()
{
	$fb = $this->context->createFbToolsLikeButton();
	$fb->setUrl('http://www.g00gl.c0m');
	return $fb;
}

protected function createComponentFbToolsScript()
{
	return $this->context->createFbToolsScript();
}

3) Template

{control likeButton, url => "http://www.anypage.com", send => false}