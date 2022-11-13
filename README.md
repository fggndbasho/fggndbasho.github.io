import NextLink from 'next/link'
import {
  Link,
  Container,
  Heading,
  Box,
  SimpleGrid,
  Button,
  List,
  ListItem,
  useColorModeValue,
  chakra
} from '@chakra-ui/react'
import { ChevronRightIcon } from '@chakra-ui/icons'
import Paragraph from '../components/paragraph'
import { BioSection, BioYear } from '../components/bio'
import Layout from '../components/layouts/article'
import Section from '../components/section'
import { GridItem } from '../components/grid-item'
import { IoLogoTwitter, IoLogoInstagram, IoLogoGithub } from 'react-icons/io5'
import thumbYouTube from '../public/images/links/youtube.png'
import thumbInkdrop from '../public/images/works/inkdrop_eyecatch.png'
import Image from 'next/image'

const ProfileImage = chakra(Image, {
  shouldForwardProp: prop => ['width', 'height', 'src', 'alt'].includes(prop)
})

const Home = () => (
  <Layout>
    <Container>
      <Box
        borderRadius="lg"
        mb={6}
        p={3}
        textAlign="center"
        bg={useColorModeValue('whiteAlpha.500', 'whiteAlpha.200')}
        css={{ backdropFilter: 'blur(10px)' }}
      >
        ¡Hola! Soy abogado por el Centro Universitario de Tonalá de la Universidad de Guadalajara.
        Sea bienvenid@ a mi sitio web personal!
      </Box>

      <Box display={{ md: 'flex' }}>
        <Box flexGrow={1}>
          <Heading as="h2" variant="page-title">
            Fernando García Gómez
          </Heading>
          <p>Licenciado en Abogado por la Universidad de Guadalajara
          </p>
        </Box>
        <Box
          flexShrink={0}
          mt={{ base: 4, md: 0 }}
          ml={{ md: 6 }}
          textAlign="center"
        >
          <Box
            borderColor="whiteAlpha.800"
            borderWidth={3}
            borderStyle="solid"
            w="100px"
            h="100px"
            display="inline-block"
            borderRadius="full"
            overflow="hidden"
          >
            <ProfileImage
              src="/images/fernando.jpg"
              alt="Profile image"
              borderRadius="full"
              width="100%"
              height="100%"
            />
          </Box>
        </Box>
      </Box>

      <Section delay={0.1}>
        <Heading as="h3" variant="section-title">
          Trabajos
        </Heading>
        <Paragraph>

          Fernando le puede ayudar a solucionar sus problemas legales de índole civiles, administrativos y constitucionales,
          así como brindar asesoría profesional personalizada, y órden a cualquier duda analítica que usted tenga. 
           
           A través del siguiente link, se puede encontrar con los resultados publicados en el tiempo libre de Fernando, como investigador autodidácta:{' '}
           
          <NextLink href="/works/inkdrop" passHref scroll={false}>
            <Link>Tesis: El Basho en la teoría jurídica moderna</Link>
          </NextLink>
          . Aquí también puede encontrar información para su 
          <NextLink href="https://www.youtube.com/devaslife" passHref>
            <Link target="_blank"> contacto</Link>
          </NextLink>
          , encontrará sus redes sociales más directas.
        </Paragraph>
        <Box align="center" my={4}>
          <NextLink href="/works" passHref scroll={false}>
            <Button rightIcon={<ChevronRightIcon />} colorScheme="teal">
              Mi portafolio
            </Button>
          </NextLink>
        </Box>
      </Section>

      <Section delay={0.2}>
        <Heading as="h3" variant="section-title">
          Bio
        </Heading>
        <BioSection>
          <BioYear>1995</BioYear>
          Nació en Guadalajara, Jalísco, México.
        </BioSection>
        <BioSection>
          <BioYear>2021</BioYear>
          Prácticas profesionales en el departamento jurídico de lo laboral burocrático en el H. Ayuntamiento
          Constitucional de Tonalá, Jalisco. Referencia de jefe directo el Dr. Francisco Javier García Escobedo.
        </BioSection>
        <BioSection>
          <BioYear>2022</BioYear>
          Titulado por la Tesis "El Basho en la teoría jurídica moderna", en el Centro Universitario de Tonalá de la Universidad de Guadalajara.
        </BioSection>

        <BioSection>
          <BioYear>2022</BioYear>
          Litigante en el despacho jurídico Gómez & Asociados.
        </BioSection>
      </Section>

      <Section delay={0.3}>
        <Heading as="h3" variant="section-title">
          Yo
        </Heading>
        <Paragraph>
          Arte, Música,{' '}
          <Link href="https://illust.odoruinu.net/" target="_blank">
            Pintura
          </Link>
          , Filosofía,{' '}
          <Link href="https://500px.com/p/craftzdog" target="_blank">
            Fotografía
          </Link>
          , Investigación, Ciencias Sociales
        </Paragraph>
      </Section>

      <Section delay={0.3}>
        <Heading as="h3" variant="section-title">
          Otros sitios web
        </Heading>
        <List>
          <ListItem>
            <Link href="https://github.com/craftzdog" target="_blank">
              <Button
                variant="ghost"
                colorScheme="teal"
                leftIcon={<IoLogoGithub />}
              >
                @craftzdog
              </Button>
            </Link>
          </ListItem>
          <ListItem>
            <Link href="https://twitter.com/inkdrop_app" target="_blank">
              <Button
                variant="ghost"
                colorScheme="teal"
                leftIcon={<IoLogoTwitter />}
              >
                @inkdrop_app (English)
              </Button>
            </Link>
          </ListItem>
          <ListItem>
            <Link href="https://twitter.com/craftzdog" target="_blank">
              <Button
                variant="ghost"
                colorScheme="teal"
                leftIcon={<IoLogoTwitter />}
              >
                @twitter
              </Button>
            </Link>
          </ListItem>
          <ListItem>
            <Link href="https://instagram.com/fgg____" target="_blank">
              <Button
                variant="ghost"
                colorScheme="teal"
                leftIcon={<IoLogoInstagram />}
              >
                @fgg____ (Fernando García Gómez)
              </Button>
            </Link>
          </ListItem>
        </List>

        <SimpleGrid columns={[1, 2, 2]} gap={6}>
          <GridItem
            href="https://www.youtube.com/devaslife"
            title="Artículo sobre vida y el derecho moderno"
            thumbnail={thumbYouTube}
          >
            Audiovisual sobre el derecho
          </GridItem>
          <GridItem
            href="https://www.inkdrop.app/"
            title="Inkdrop"
            thumbnail={thumbInkdrop}
          >
            A Markdown note-taking app
          </GridItem>
        </SimpleGrid>

        <Box align="center" my={4}>
          <NextLink href="/posts" passHref scroll={false}>
            <Button rightIcon={<ChevronRightIcon />} colorScheme="teal">
              Publicaciones populares
            </Button>
          </NextLink>
        </Box>
      </Section>
    </Container>
  </Layout>
)

export default Home
export { getServerSideProps } from '../components/chakra'
