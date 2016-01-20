Esta é uma mini instalação de SF 2.5 utilizada apenas para gerar reversa do banco de dados,
e o json schema das entidades para validação no frontend.

Clone, crie seu bundle e adicione a configuração abaixo para que o json_schema seja gerado

//src/MyBundle/MyBundle.php
use Symfony\Component\DependencyInjection\ContainerBuilder;
...
public function build(ContainerBuilder $container)
{
    $container->addCompilerPass(new \Knp\JsonSchemaBundle\DependencyInjection\Compiler\RegisterJsonSchemasPass($this));
}